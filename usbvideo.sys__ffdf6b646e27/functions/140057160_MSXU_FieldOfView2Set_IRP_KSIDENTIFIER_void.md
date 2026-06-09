# MSXU_FieldOfView2Set(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140057160`
- end: `0x14005746a`
- name: `?MSXU_FieldOfView2Set@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `778`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14001d120`
- `0x140057160`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_FieldOfView2Set(struct _IRP *a1, struct KSIDENTIFIER *a2, _DWORD *a3)
{
  NTSTATUS v6; // ebx
  unsigned int v7; // r8d
  struct _HW_DEVICE_EXTENSION *v8; // r14
  __int64 v9; // r15
  int v10; // ebx
  unsigned int i; // edx
  __int64 v12; // r9
  unsigned __int8 v13; // r9
  int v14; // eax
  int v16; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  struct _TOPOLOGY_NODE_INFO *v18; // [rsp+38h] [rbp-38h]
  struct _HW_DEVICE_EXTENSION *v19; // [rsp+50h] [rbp-20h] BYREF
  struct _KSFILTER *v20; // [rsp+58h] [rbp-18h] BYREF
  struct _TOPOLOGY_NODE_INFO *v21; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 v22; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int8 v23; // [rsp+C8h] [rbp+58h] BYREF

  v23 = 0;
  v22 = 0;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 278, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  if ( a1 && a2 && a3 )
  {
    v6 = MSXUGetInfo(a1, &v20, &v23, &v22, &v21, &v19);
    if ( v6 >= 0 )
    {
      v6 = ValidateExtendedPropertyDataBufferLength(a1, a3, 40);
      if ( v6 >= 0 )
      {
        if ( *a3 == 1 && a3[2] >= v7 && a3[1] == -1 )
        {
          v8 = v19;
          v9 = *((_QWORD *)v19 + 134);
          v10 = *((unsigned __int16 *)v19 + 627);
          if ( (!v9 || !(_WORD)v10)
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 282, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
          }
          for ( i = 0; i < (v10 - 4) / 4; ++i )
          {
            v12 = (unsigned int)a3[8];
            if ( *(_DWORD *)(v9 + (unsigned int)(2 * v10) + 4LL * i + 4) == (_DWORD)v12 )
            {
              LODWORD(v19) = a3[8];
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 283, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v12);
              v13 = v23;
              *((_QWORD *)v8 + 152) = v20;
              v18 = v21;
              LODWORD(Size) = 4;
              LOBYTE(v16) = v22;
              *((_DWORD *)v8 + 335) = 1;
              v14 = SubmitControlRequest(
                      0x21u,
                      1u,
                      0x1000u,
                      v13,
                      v16,
                      (unsigned __int8 *)&v19,
                      Size,
                      (__int64)v18,
                      (__int64)v8);
              v6 = v14;
              if ( v14 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    284,
                    WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
                    (unsigned int)v14);
                *((_QWORD *)v8 + 152) = 0;
              }
              else
              {
                a1->IoStatus.Information = 40;
              }
              goto LABEL_40;
            }
          }
        }
        v6 = -1073741811;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_43;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 281, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_43;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 280, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
    }
  }
  else
  {
    v6 = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_43;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 279, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1, a2, a3);
  }
LABEL_40:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 285, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v6);
LABEL_43:
  a1->IoStatus.Status = v6;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140057160  mov     [rsp-38h+arg_8], rbx
0x140057165  push    rbp
0x140057166  push    rsi
0x140057167  push    rdi
0x140057168  push    r12
0x14005716a  push    r13
0x14005716c  push    r14
0x14005716e  push    r15
0x140057170  mov     rbp, rsp
0x140057173  sub     rsp, 70h
0x140057177  xor     r12d, r12d
0x14005717a  mov     rsi, r8
0x14005717d  mov     [rbp+arg_18], r12b
0x140057181  mov     r14, rdx
0x140057184  mov     [rbp+arg_0], r12b
0x140057188  mov     rdi, rcx
0x14005718b  mov     [rbp+var_10], r12
0x14005718f  mov     [rbp+var_20], r12
0x140057193  mov     [rbp+var_18], r12
0x140057197  mov     rcx, cs:WPP_GLOBAL_Control
0x14005719e  lea     r13, WPP_GLOBAL_Control
0x1400571a5  lea     r15d, [r12+4]
0x1400571aa  cmp     rcx, r13
0x1400571ad  jz      short loc_1400571CD
0x1400571af  cmp     [rcx+29h], r15b
0x1400571b3  jb      short loc_1400571CD
0x1400571b5  mov     rcx, [rcx+18h]
0x1400571b9  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400571c0  mov     edx, 116h
0x1400571c5  mov     r9, rdi
0x1400571c8  call    WPP_SF_q
0x1400571cd  test    rdi, rdi
0x1400571d0  jz      loc_1400573E9
0x1400571d6  test    r14, r14
0x1400571d9  jz      loc_1400573E9
0x1400571df  test    rsi, rsi
0x1400571e2  jz      loc_1400573E9
0x1400571e8  lea     rax, [rbp+var_20]
0x1400571ec  mov     rcx, rdi; struct _IRP *
0x1400571ef  mov     [rsp+70h+var_48], rax; struct _HW_DEVICE_EXTENSION **
0x1400571f4  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x1400571f8  lea     rax, [rbp+var_10]
0x1400571fc  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x140057200  mov     [rsp+70h+var_50], rax; struct _TOPOLOGY_NODE_INFO **
0x140057205  lea     rdx, [rbp+var_18]; struct _KSFILTER **
0x140057209  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x14005720e  mov     ebx, eax
0x140057210  test    eax, eax
0x140057212  jns     short loc_14005724B
0x140057214  mov     rcx, cs:WPP_GLOBAL_Control
0x14005721b  cmp     rcx, r13
0x14005721e  jz      loc_14005744C
0x140057224  cmp     byte ptr [rcx+29h], 2
0x140057228  jb      loc_140057422
0x14005722e  mov     rcx, [rcx+18h]
0x140057232  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057239  mov     edx, 118h
0x14005723e  mov     r9, rdi
0x140057241  call    WPP_SF_q
0x140057246  jmp     loc_140057422
0x14005724b  xor     r9d, r9d
0x14005724e  mov     rdx, rsi
0x140057251  mov     rcx, rdi
0x140057254  lea     r8d, [r9+28h]
0x140057258  call    ValidateExtendedPropertyDataBufferLength
0x14005725d  mov     ebx, eax
0x14005725f  test    eax, eax
0x140057261  jns     short loc_140057297
0x140057263  mov     rcx, cs:WPP_GLOBAL_Control
0x14005726a  cmp     rcx, r13
0x14005726d  jz      loc_14005744C
0x140057273  cmp     byte ptr [rcx+29h], 2
0x140057277  jb      loc_140057422
0x14005727d  mov     rcx, [rcx+18h]
0x140057281  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057288  mov     edx, 119h
0x14005728d  call    WPP_SF_
0x140057292  jmp     loc_140057422
0x140057297  cmp     dword ptr [rsi], 1
0x14005729a  jnz     loc_1400573E2
0x1400572a0  cmp     [rsi+8], r8d
0x1400572a4  jb      loc_1400573E2
0x1400572aa  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x1400572ae  jnz     loc_1400573E2
0x1400572b4  mov     r14, [rbp+var_20]
0x1400572b8  mov     r15, [r14+430h]
0x1400572bf  movzx   ebx, word ptr [r14+4E6h]
0x1400572c7  test    r15, r15
0x1400572ca  jz      short loc_1400572D1
0x1400572cc  test    bx, bx
0x1400572cf  jnz     short loc_1400572F8
0x1400572d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400572d8  cmp     rcx, r13
0x1400572db  jz      short loc_1400572F8
0x1400572dd  cmp     byte ptr [rcx+29h], 2
0x1400572e1  jb      short loc_1400572F8
0x1400572e3  mov     rcx, [rcx+18h]
0x1400572e7  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400572ee  mov     edx, 11Ah
0x1400572f3  call    WPP_SF_
0x1400572f8  lea     r8d, [rbx+rbx]
0x1400572fc  add     r8, r15
0x1400572ff  lea     eax, [rbx-4]
0x140057302  mov     r15d, 4
0x140057308  cdq
0x140057309  idiv    r15d
0x14005730c  mov     edx, r12d
0x14005730f  cmp     edx, eax
0x140057311  jnb     loc_1400573E2
0x140057317  mov     r9d, [rsi+20h]
0x14005731b  mov     ecx, edx
0x14005731d  cmp     [r8+rcx*4+4], r9d
0x140057322  jz      short loc_140057328
0x140057324  inc     edx
0x140057326  jmp     short loc_14005730F
0x140057328  mov     dword ptr [rbp+var_20], r9d
0x14005732c  mov     rcx, cs:WPP_GLOBAL_Control
0x140057333  cmp     rcx, r13
0x140057336  jz      short loc_140057353
0x140057338  cmp     [rcx+29h], r15b
0x14005733c  jb      short loc_140057353
0x14005733e  mov     rcx, [rcx+18h]
0x140057342  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057349  mov     edx, 11Bh
0x14005734e  call    WPP_SF_d
0x140057353  mov     rax, [rbp+var_18]
0x140057357  mov     r8d, 1000h; int
0x14005735d  mov     r9b, [rbp+arg_18]; int
0x140057361  mov     dl, 1; int
0x140057363  mov     [r14+4C0h], rax
0x14005736a  mov     cl, 21h ; '!'; int
0x14005736c  mov     rax, [rbp+var_10]
0x140057370  mov     [rsp+70h+var_30], r14; __int64
0x140057375  mov     [rsp+70h+var_38], rax; __int64
0x14005737a  lea     rax, [rbp+var_20]
0x14005737e  mov     dword ptr [rsp+70h+Size], r15d; Size
0x140057383  mov     [rsp+70h+var_48], rax; void *
0x140057388  mov     al, [rbp+arg_0]
0x14005738b  mov     byte ptr [rsp+70h+var_50], al; int
0x14005738f  mov     dword ptr [r14+53Ch], 1
0x14005739a  call    SubmitControlRequest
0x14005739f  mov     ebx, eax
0x1400573a1  test    eax, eax
0x1400573a3  js      short loc_1400573AF
0x1400573a5  mov     qword ptr [rdi+38h], 28h ; '('
0x1400573ad  jmp     short loc_140057422
0x1400573af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400573b6  cmp     rcx, r13
0x1400573b9  jz      short loc_1400573D9
0x1400573bb  cmp     byte ptr [rcx+29h], 2
0x1400573bf  jb      short loc_1400573D9
0x1400573c1  mov     rcx, [rcx+18h]
0x1400573c5  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400573cc  mov     edx, 11Ch
0x1400573d1  mov     r9d, eax
0x1400573d4  call    WPP_SF_d
0x1400573d9  mov     [r14+4C0h], r12
0x1400573e0  jmp     short loc_140057422
0x1400573e2  mov     ebx, 0C000000Dh
0x1400573e7  jmp     short loc_140057422
0x1400573e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400573f0  mov     ebx, 0C0000001h
0x1400573f5  cmp     rcx, r13
0x1400573f8  jz      short loc_14005744C
0x1400573fa  cmp     byte ptr [rcx+29h], 2
0x1400573fe  jb      short loc_140057422
0x140057400  mov     rcx, [rcx+18h]
0x140057404  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005740b  mov     edx, 117h
0x140057410  mov     [rsp+70h+var_48], rsi
0x140057415  mov     r9, rdi
0x140057418  mov     [rsp+70h+var_50], r14
0x14005741d  call    WPP_SF_qqq
0x140057422  mov     rcx, cs:WPP_GLOBAL_Control
0x140057429  cmp     rcx, r13
0x14005742c  jz      short loc_14005744C
0x14005742e  cmp     [rcx+29h], r15b
0x140057432  jb      short loc_14005744C
0x140057434  mov     rcx, [rcx+18h]
0x140057438  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005743f  mov     edx, 11Dh
0x140057444  mov     r9d, ebx
0x140057447  call    WPP_SF_d
0x14005744c  mov     [rdi+30h], ebx
0x14005744f  mov     eax, ebx
0x140057451  mov     rbx, [rsp+70h+arg_8]
0x140057459  add     rsp, 70h
0x14005745d  pop     r15
0x14005745f  pop     r14
0x140057461  pop     r13
0x140057463  pop     r12
0x140057465  pop     rdi
0x140057466  pop     rsi
0x140057467  pop     rbp
0x140057468  retn
```
