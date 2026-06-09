# MSXU_DigitalWindowConfigGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140055470`
- end: `0x14005586b`
- name: `?MSXU_DigitalWindowConfigGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `1019`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14001d0cc`
- `0x14003b508`
- `0x140040e40`
- `0x140055470`
- `0x14005bd18`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400557cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400557cd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400555f4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400555f4`

## pseudocode

```c
__int64 __fastcall MSXU_DigitalWindowConfigGet(struct _IRP *a1, struct KSIDENTIFIER *a2, _DWORD *a3)
{
  struct _IRP *v5; // rsi
  int v6; // ebx
  SIZE_T v7; // r12
  unsigned int v8; // r15d
  unsigned int v9; // r13d
  unsigned __int8 *PoolWithTag; // rax
  unsigned __int8 *v11; // r14
  __int64 v12; // r8
  unsigned int v13; // r12d
  int v14; // eax
  __int64 v15; // r13
  __int64 v16; // rcx
  int v18; // [rsp+20h] [rbp-49h]
  size_t Size; // [rsp+30h] [rbp-39h]
  unsigned __int8 v20[4]; // [rsp+70h] [rbp+7h] BYREF
  int v21; // [rsp+74h] [rbp+Bh]
  struct _KSFILTER *v22; // [rsp+78h] [rbp+Fh] BYREF
  struct _HW_DEVICE_EXTENSION *v23; // [rsp+80h] [rbp+17h] BYREF
  struct _TOPOLOGY_NODE_INFO *v24; // [rsp+88h] [rbp+1Fh] BYREF
  unsigned __int8 v26; // [rsp+E8h] [rbp+7Fh] BYREF

  v20[0] = 0;
  v26 = 0;
  v5 = a1;
  v24 = 0;
  v23 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 214, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  if ( v5 && a2 )
  {
    v6 = MSXUGetInfo(v5, &v22, v20, &v26, &v24, &v23);
    if ( v6 >= 0 )
    {
      v7 = *((unsigned __int16 *)v23 + 624);
      v8 = *((unsigned __int16 *)v23 + 624) / 0x24u;
      v21 = 40 * v8;
      v9 = 40 * v8 + 40;
      LODWORD(v22) = v9;
      v6 = ValidateExtendedPropertyDataBufferLength(v5, a3, v9);
      if ( v6 >= 0 )
      {
        v6 = -1073741670;
        PoolWithTag = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)1536, v7, 0x56425355u);
        v11 = PoolWithTag;
        if ( PoolWithTag )
        {
          if ( !ExPoolZeroingNativelySupported )
            memset(PoolWithTag, 0, v7);
          LODWORD(Size) = v7;
          LOBYTE(v18) = v26;
          v6 = SubmitControlRequest(0xA1u, 0x81u, 0xC00u, v20[0], v18, v11, Size, (__int64)v24, (__int64)v23);
          if ( v6 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 219, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
          }
          else
          {
            v13 = 0;
            v14 = v21 + 8;
            *a3 = 1;
            a3[1] = -1;
            a3[3] = 0;
            *((_QWORD *)a3 + 2) = 0;
            *((_QWORD *)a3 + 3) = 0;
            a3[2] = v9;
            a3[8] = v14;
            a3[9] = v8;
            if ( v8 )
            {
              v15 = 0;
              do
              {
                v16 = 5 * v15;
                a3[2 * v16 + 10] = *(_DWORD *)&v11[36 * v15];
                a3[2 * v16 + 11] = *(_DWORD *)&v11[36 * v15 + 4];
                a3[2 * v16 + 12] = *(_DWORD *)&v11[36 * v15 + 12];
                a3[2 * v16 + 13] = *(_DWORD *)&v11[36 * v15 + 8];
                a3[2 * v16 + 14] = *(_DWORD *)&v11[36 * v15 + 20];
                a3[2 * v16 + 15] = *(_DWORD *)&v11[36 * v15 + 16];
                a3[2 * v16 + 16] = *(_DWORD *)&v11[36 * v15 + 24];
                a3[2 * v16 + 17] = *(_DWORD *)&v11[36 * v15 + 28];
                a3[2 * v16 + 18] = *(_DWORD *)&v11[36 * v15 + 32];
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  WPP_SF_dddDDDDDDD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    9 * v15,
                    v12,
                    v13,
                    *(_DWORD *)&v11[36 * v15],
                    *(_DWORD *)&v11[36 * v15 + 4],
                    *(_DWORD *)&v11[36 * v15 + 12],
                    *(_DWORD *)&v11[36 * v15 + 8],
                    *(_DWORD *)&v11[36 * v15 + 20],
                    *(_DWORD *)&v11[36 * v15 + 16],
                    *(_DWORD *)&v11[36 * v15 + 24],
                    *(_DWORD *)&v11[36 * v15 + 28],
                    *(_DWORD *)&v11[36 * v15 + 32]);
                ++v13;
                ++v15;
              }
              while ( v13 < v8 );
              v5 = a1;
              v9 = (unsigned int)v22;
            }
            v5->IoStatus.Information = v9;
          }
          ExFreePoolWithTag(v11, 0x56425355u);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_33;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 217, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_33;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 216, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v5);
    }
  }
  else
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_33;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 215, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v5, a2);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 220, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v6);
LABEL_33:
  v5->IoStatus.Status = v6;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140055470  mov     [rsp-8+arg_8], rbx
0x140055475  mov     [rsp-8+arg_0], rcx
0x14005547a  push    rbp
0x14005547b  push    rsi
0x14005547c  push    rdi
0x14005547d  push    r12
0x14005547f  push    r13
0x140055481  push    r14
0x140055483  push    r15
0x140055485  lea     rbp, [rsp-27h]
0x14005548a  sub     rsp, 90h
0x140055491  xor     r15d, r15d
0x140055494  mov     rdi, r8
0x140055497  mov     [rbp+57h+var_50], r15b
0x14005549b  mov     r14, rdx
0x14005549e  mov     [rbp+57h+arg_18], r15b
0x1400554a2  mov     rsi, rcx
0x1400554a5  mov     [rbp+57h+var_38], r15
0x1400554a9  mov     [rbp+57h+var_40], r15
0x1400554ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400554b4  lea     rbx, WPP_GLOBAL_Control
0x1400554bb  mov     r12b, 2
0x1400554be  cmp     rcx, rbx
0x1400554c1  jz      short loc_1400554E1
0x1400554c3  cmp     [rcx+29h], r12b
0x1400554c7  jb      short loc_1400554E1
0x1400554c9  mov     rcx, [rcx+18h]
0x1400554cd  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400554d4  mov     edx, 0D6h
0x1400554d9  mov     r9, rsi
0x1400554dc  call    WPP_SF_q
0x1400554e1  test    rsi, rsi
0x1400554e4  jz      loc_14005582B
0x1400554ea  test    r14, r14
0x1400554ed  jz      loc_14005582B
0x1400554f3  lea     rax, [rbp+57h+var_40]
0x1400554f7  mov     rcx, rsi; struct _IRP *
0x1400554fa  mov     [rsp+0C0h+var_98], rax; struct _HW_DEVICE_EXTENSION **
0x1400554ff  lea     r9, [rbp+57h+arg_18]; unsigned __int8 *
0x140055503  lea     rax, [rbp+57h+var_38]
0x140055507  lea     r8, [rbp+57h+var_50]; unsigned __int8 *
0x14005550b  mov     [rsp+0C0h+var_A0], rax; struct _TOPOLOGY_NODE_INFO **
0x140055510  lea     rdx, [rbp+57h+var_48]; struct _KSFILTER **
0x140055514  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140055519  mov     ebx, eax
0x14005551b  test    eax, eax
0x14005551d  jns     short loc_14005555D
0x14005551f  mov     rcx, cs:WPP_GLOBAL_Control
0x140055526  lea     rdi, WPP_GLOBAL_Control
0x14005552d  cmp     rcx, rdi
0x140055530  jz      loc_14005580A
0x140055536  cmp     [rcx+29h], r12b
0x14005553a  jb      loc_1400557E0
0x140055540  mov     rcx, [rcx+18h]
0x140055544  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005554b  mov     edx, 0D8h
0x140055550  mov     r9, rsi
0x140055553  call    WPP_SF_q
0x140055558  jmp     loc_1400557E0
0x14005555d  mov     rax, [rbp+57h+var_40]
0x140055561  xor     r9d, r9d
0x140055564  mov     rcx, rsi
0x140055567  movzx   r12d, word ptr [rax+4E0h]
0x14005556f  mov     rax, 0E38E38E38E38E38Fh
0x140055579  mul     r12
0x14005557c  mov     r15, rdx
0x14005557f  mov     rdx, rdi
0x140055582  shr     r15, 5
0x140055586  lea     eax, [r15+r15*4]
0x14005558a  shl     eax, 3
0x14005558d  mov     [rbp+57h+var_4C], eax
0x140055590  lea     r13d, [rax+28h]
0x140055594  mov     r8d, r13d
0x140055597  mov     dword ptr [rbp+57h+var_48], r13d
0x14005559b  call    ValidateExtendedPropertyDataBufferLength
0x1400555a0  mov     ebx, eax
0x1400555a2  test    eax, eax
0x1400555a4  jns     short loc_1400555E1
0x1400555a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400555ad  lea     rdi, WPP_GLOBAL_Control
0x1400555b4  cmp     rcx, rdi
0x1400555b7  jz      loc_14005580A
0x1400555bd  cmp     byte ptr [rcx+29h], 4
0x1400555c1  jb      loc_1400557E0
0x1400555c7  mov     rcx, [rcx+18h]
0x1400555cb  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400555d2  mov     edx, 0D9h
0x1400555d7  call    WPP_SF_
0x1400555dc  jmp     loc_1400557E0
0x1400555e1  mov     r8d, 56425355h; Tag
0x1400555e7  mov     rdx, r12; NumberOfBytes
0x1400555ea  mov     ecx, 600h; PoolType
0x1400555ef  mov     ebx, 0C000009Ah
0x1400555f4  call    cs:__imp_ExAllocatePoolWithTag
0x1400555fb  nop     dword ptr [rax+rax+00h]
0x140055600  mov     r14, rax
0x140055603  test    rax, rax
0x140055606  jz      loc_1400557D9
0x14005560c  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140055613  jnz     short loc_140055622
0x140055615  mov     r8, r12; Size
0x140055618  xor     edx, edx; Val
0x14005561a  mov     rcx, rax; void *
0x14005561d  call    memset
0x140055622  mov     rax, [rbp+57h+var_40]
0x140055626  mov     r8d, 0C00h; int
0x14005562c  mov     r9b, [rbp+57h+var_50]; int
0x140055630  mov     dl, 81h; int
0x140055632  mov     [rsp+0C0h+var_80], rax; __int64
0x140055637  mov     cl, 0A1h; int
0x140055639  mov     rax, [rbp+57h+var_38]
0x14005563d  mov     [rsp+0C0h+var_88], rax; __int64
0x140055642  mov     al, [rbp+57h+arg_18]
0x140055645  mov     dword ptr [rsp+0C0h+Size], r12d; Size
0x14005564a  mov     [rsp+0C0h+var_98], r14; void *
0x14005564f  mov     byte ptr [rsp+0C0h+var_A0], al; int
0x140055653  call    SubmitControlRequest
0x140055658  xor     ecx, ecx
0x14005565a  mov     ebx, eax
0x14005565c  test    eax, eax
0x14005565e  js      loc_140055797
0x140055664  mov     eax, [rbp+57h+var_4C]
0x140055667  mov     r12d, ecx
0x14005566a  add     eax, 8
0x14005566d  mov     dword ptr [rdi], 1
0x140055673  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x14005567a  mov     [rdi+0Ch], ecx
0x14005567d  mov     [rdi+10h], rcx
0x140055681  mov     [rdi+18h], rcx
0x140055685  mov     [rdi+8], r13d
0x140055689  mov     [rdi+20h], eax
0x14005568c  mov     [rdi+24h], r15d
0x140055690  test    r15d, r15d
0x140055693  jz      loc_14005578E
0x140055699  mov     r13d, ecx
0x14005569c  lea     rsi, WPP_GLOBAL_Control
0x1400556a3  lea     rdx, ds:0[r13*8]
0x1400556ab  add     rdx, r13
0x1400556ae  lea     rcx, ds:0[r13*4]
0x1400556b6  add     rcx, r13
0x1400556b9  mov     eax, [r14+rdx*4]
0x1400556bd  mov     [rdi+rcx*8+28h], eax
0x1400556c1  mov     eax, [r14+rdx*4+4]
0x1400556c6  mov     [rdi+rcx*8+2Ch], eax
0x1400556ca  mov     eax, [r14+rdx*4+0Ch]
0x1400556cf  mov     [rdi+rcx*8+30h], eax
0x1400556d3  mov     eax, [r14+rdx*4+8]
0x1400556d8  mov     [rdi+rcx*8+34h], eax
0x1400556dc  mov     eax, [r14+rdx*4+14h]
0x1400556e1  mov     [rdi+rcx*8+38h], eax
0x1400556e5  mov     eax, [r14+rdx*4+10h]
0x1400556ea  mov     [rdi+rcx*8+3Ch], eax
0x1400556ee  mov     eax, [r14+rdx*4+18h]
0x1400556f3  mov     [rdi+rcx*8+40h], eax
0x1400556f7  mov     eax, [r14+rdx*4+1Ch]
0x1400556fc  mov     [rdi+rcx*8+44h], eax
0x140055700  mov     eax, [r14+rdx*4+20h]
0x140055705  mov     [rdi+rcx*8+48h], eax
0x140055709  mov     rcx, cs:WPP_GLOBAL_Control
0x140055710  cmp     rcx, rsi
0x140055713  jz      short loc_140055777
0x140055715  cmp     byte ptr [rcx+29h], 4
0x140055719  jb      short loc_140055777
0x14005571b  mov     eax, [r14+rdx*4+20h]
0x140055720  mov     r9d, r12d
0x140055723  mov     rcx, [rcx+18h]
0x140055727  mov     [rsp+0C0h+var_60], eax
0x14005572b  mov     eax, [r14+rdx*4+1Ch]
0x140055730  mov     [rsp+0C0h+var_68], eax
0x140055734  mov     eax, [r14+rdx*4+18h]
0x140055739  mov     [rsp+0C0h+var_70], eax
0x14005573d  mov     eax, [r14+rdx*4+10h]
0x140055742  mov     [rsp+0C0h+var_78], eax
0x140055746  mov     eax, [r14+rdx*4+14h]
0x14005574b  mov     dword ptr [rsp+0C0h+var_80], eax
0x14005574f  mov     eax, [r14+rdx*4+8]
0x140055754  mov     dword ptr [rsp+0C0h+var_88], eax
0x140055758  mov     eax, [r14+rdx*4+0Ch]
0x14005575d  mov     dword ptr [rsp+0C0h+Size], eax
0x140055761  mov     eax, [r14+rdx*4+4]
0x140055766  mov     dword ptr [rsp+0C0h+var_98], eax
0x14005576a  mov     eax, [r14+rdx*4]
0x14005576e  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140055772  call    WPP_SF_dddDDDDDDD
0x140055777  inc     r12d
0x14005577a  inc     r13
0x14005577d  cmp     r12d, r15d
0x140055780  jb      loc_1400556A3
0x140055786  mov     rsi, [rbp+57h+arg_0]
0x14005578a  mov     r13d, dword ptr [rbp+57h+var_48]
0x14005578e  mov     eax, r13d
0x140055791  mov     [rsi+38h], rax
0x140055795  jmp     short loc_1400557C5
0x140055797  mov     rcx, cs:WPP_GLOBAL_Control
0x14005579e  lea     rax, WPP_GLOBAL_Control
0x1400557a5  cmp     rcx, rax
0x1400557a8  jz      short loc_1400557C5
0x1400557aa  cmp     byte ptr [rcx+29h], 2
0x1400557ae  jb      short loc_1400557C5
0x1400557b0  mov     rcx, [rcx+18h]
0x1400557b4  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400557bb  mov     edx, 0DBh
0x1400557c0  call    WPP_SF_
0x1400557c5  mov     edx, 56425355h; Tag
0x1400557ca  mov     rcx, r14; P
0x1400557cd  call    cs:__imp_ExFreePoolWithTag
0x1400557d4  nop     dword ptr [rax+rax+00h]
0x1400557d9  lea     rdi, WPP_GLOBAL_Control
0x1400557e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400557e7  cmp     rcx, rdi
0x1400557ea  jz      short loc_14005580A
0x1400557ec  cmp     byte ptr [rcx+29h], 4
0x1400557f0  jb      short loc_14005580A
0x1400557f2  mov     rcx, [rcx+18h]
0x1400557f6  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400557fd  mov     edx, 0DCh
0x140055802  mov     r9d, ebx
0x140055805  call    WPP_SF_d
0x14005580a  mov     [rsi+30h], ebx
0x14005580d  mov     eax, ebx
0x14005580f  mov     rbx, [rsp+0C0h+arg_8]
0x140055817  add     rsp, 90h
0x14005581e  pop     r15
0x140055820  pop     r14
0x140055822  pop     r13
0x140055824  pop     r12
0x140055826  pop     rdi
0x140055827  pop     rsi
0x140055828  pop     rbp
0x140055829  retn
0x14005582b  mov     rcx, cs:WPP_GLOBAL_Control
0x140055832  lea     rdi, WPP_GLOBAL_Control
0x140055839  mov     ebx, 0C000000Dh
0x14005583e  cmp     rcx, rdi
0x140055841  jz      short loc_14005580A
0x140055843  cmp     [rcx+29h], r12b
0x140055847  jb      short loc_1400557E0
0x140055849  mov     rcx, [rcx+18h]
0x14005584d  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140055854  mov     edx, 0D7h
0x140055859  mov     [rsp+0C0h+var_A0], r14
0x14005585e  mov     r9, rsi
0x140055861  call    WPP_SF_qq
0x140055866  jmp     loc_1400557E0
```
