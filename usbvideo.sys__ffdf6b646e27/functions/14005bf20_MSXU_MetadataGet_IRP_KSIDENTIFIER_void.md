# MSXU_MetadataGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14005bf20`
- end: `0x14005c1c6`
- name: `?MSXU_MetadataGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `678`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14003bb60`
- `0x14005bf20`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14005bf6b`
- `ks!KsGetFilterFromIrp` at `0x14005bf6b`

## pseudocode

```c
__int64 __fastcall MSXU_MetadataGet(PIRP Irp, struct KSIDENTIFIER *a2, _DWORD *a3)
{
  PKSFILTER FilterFromIrp; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  PKSFILTER v8; // r14
  __int64 v9; // rbp
  __int64 v10; // r15
  int v11; // r13d
  int v12; // r12d
  NTSTATUS v13; // edi
  int v14; // r8d
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  unsigned __int8 *v17; // r14
  int v18; // ecx
  int v19; // eax
  int v21; // [rsp+20h] [rbp-78h]
  int v22; // [rsp+20h] [rbp-78h]
  size_t Size; // [rsp+30h] [rbp-68h]
  size_t Sizea; // [rsp+30h] [rbp-68h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, Irp);
  FilterFromIrp = KsGetFilterFromIrp(Irp);
  v8 = FilterFromIrp;
  if ( !FilterFromIrp )
  {
    v13 = -1073741823;
    goto LABEL_30;
  }
  v9 = *(_QWORD *)FilterFromIrp->Context;
  v10 = *(_QWORD *)(v9 + 880);
  v11 = *(unsigned __int8 *)(v10 + 40);
  v12 = *(unsigned __int8 *)(*(_QWORD *)(v10 + 32) + 3LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qDDqq(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v7,
      FilterFromIrp,
      v12,
      v11,
      v10,
      *(_QWORD *)FilterFromIrp->Context);
  v13 = ValidateExtendedPropertyDataBufferLength(Irp, a3, 40);
  if ( v13 >= 0 )
  {
    if ( *a3 == 1 && a3[2] == v14 && a3[1] < v8->Descriptor->PinDescriptorsCount )
    {
      v17 = (unsigned __int8 *)(*(_QWORD *)(v9 + 1024) + 4LL);
      LODWORD(Size) = 4;
      LOBYTE(v21) = v11;
      v13 = SubmitControlRequest(0xA1u, 0x83u, 0x900u, v12, v21, v17, Size, v10, v9);
      if ( v13 >= 0 )
      {
        if ( (*(_BYTE *)(v9 + 1267) & 2) == 0
          || (LODWORD(Sizea) = 4,
              LOBYTE(v22) = v11,
              *(_DWORD *)(v9 + 1312) = 1,
              v13 = SubmitControlRequest(0x21u, 1u, 0x900u, v12, v22, v17, Sizea, v10, v9),
              v13 >= 0) )
        {
          v18 = *(_DWORD *)v17;
          v19 = a3[1];
          *a3 = 1;
          a3[1] = v19;
          *((_QWORD *)a3 + 1) = 40;
          *((_QWORD *)a3 + 2) = 1;
          *((_QWORD *)a3 + 3) = 0;
          a3[8] = 0;
          a3[9] = v18 << 10;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              157,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              *(unsigned int *)v17);
          Irp->IoStatus.Information = 40;
          goto LABEL_30;
        }
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_33;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_30;
      v16 = 158;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      v13 = -1073741811;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_33;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_30;
      v16 = 159;
    }
    goto LABEL_12;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_33;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v16 = (unsigned int)(v14 + 116);
LABEL_12:
    WPP_SF_(v15->AttachedDevice, v16, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_30:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      160,
      WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
      (unsigned int)v13);
LABEL_33:
  Irp->IoStatus.Status = v13;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14005bf20  push    rbx
0x14005bf22  push    rbp
0x14005bf23  push    rsi
0x14005bf24  push    rdi
0x14005bf25  push    r12
0x14005bf27  push    r13
0x14005bf29  push    r14
0x14005bf2b  push    r15
0x14005bf2d  sub     rsp, 58h
0x14005bf31  mov     rbx, r8
0x14005bf34  mov     rsi, rcx
0x14005bf37  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bf3e  lea     rdi, WPP_GLOBAL_Control
0x14005bf45  cmp     rcx, rdi
0x14005bf48  jz      short loc_14005BF68
0x14005bf4a  cmp     byte ptr [rcx+29h], 2
0x14005bf4e  jb      short loc_14005BF68
0x14005bf50  mov     rcx, [rcx+18h]
0x14005bf54  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005bf5b  mov     edx, 9Bh
0x14005bf60  mov     r9, rsi
0x14005bf63  call    WPP_SF_q
0x14005bf68  mov     rcx, rsi; Irp
0x14005bf6b  call    cs:__imp_KsGetFilterFromIrp
0x14005bf72  nop     dword ptr [rax+rax+00h]
0x14005bf77  mov     r14, rax
0x14005bf7a  test    rax, rax
0x14005bf7d  jz      loc_14005C179
0x14005bf83  mov     rcx, [rax+10h]
0x14005bf87  mov     rbp, [rcx]
0x14005bf8a  mov     r15, [rbp+370h]
0x14005bf91  mov     rcx, [r15+20h]
0x14005bf95  movzx   r13d, byte ptr [r15+28h]
0x14005bf9a  movzx   r12d, byte ptr [rcx+3]
0x14005bf9f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bfa6  cmp     rcx, rdi
0x14005bfa9  jz      short loc_14005BFD1
0x14005bfab  cmp     byte ptr [rcx+29h], 5
0x14005bfaf  jb      short loc_14005BFD1
0x14005bfb1  mov     rcx, [rcx+18h]
0x14005bfb5  mov     r9, rax
0x14005bfb8  mov     [rsp+98h+var_60], rbp
0x14005bfbd  mov     [rsp+98h+Size], r15
0x14005bfc2  mov     dword ptr [rsp+98h+var_70], r13d
0x14005bfc7  mov     [rsp+98h+var_78], r12d
0x14005bfcc  call    WPP_SF_qDDqq
0x14005bfd1  xor     r9d, r9d
0x14005bfd4  mov     rdx, rbx
0x14005bfd7  mov     rcx, rsi
0x14005bfda  lea     r8d, [r9+28h]
0x14005bfde  call    ValidateExtendedPropertyDataBufferLength
0x14005bfe3  mov     edi, eax
0x14005bfe5  test    eax, eax
0x14005bfe7  jns     short loc_14005C023
0x14005bfe9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bff0  lea     rbx, WPP_GLOBAL_Control
0x14005bff7  cmp     rcx, rbx
0x14005bffa  jz      loc_14005C1AF
0x14005c000  cmp     byte ptr [rcx+29h], 2
0x14005c004  jb      loc_14005C185
0x14005c00a  lea     edx, [r8+74h]
0x14005c00e  mov     rcx, [rcx+18h]
0x14005c012  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c019  call    WPP_SF_
0x14005c01e  jmp     loc_14005C185
0x14005c023  cmp     dword ptr [rbx], 1
0x14005c026  jnz     loc_14005C151
0x14005c02c  cmp     [rbx+8], r8d
0x14005c030  jnz     loc_14005C151
0x14005c036  mov     rax, [r14]
0x14005c039  mov     ecx, [rax+20h]
0x14005c03c  cmp     [rbx+4], ecx
0x14005c03f  jnb     loc_14005C151
0x14005c045  mov     r14, [rbp+400h]
0x14005c04c  mov     r8d, 900h; int
0x14005c052  mov     [rsp+98h+var_58], rbp; __int64
0x14005c057  add     r14, 4
0x14005c05b  mov     [rsp+98h+var_60], r15; __int64
0x14005c060  mov     r9b, r12b; int
0x14005c063  mov     dword ptr [rsp+98h+Size], 4; Size
0x14005c06b  mov     dl, 83h; int
0x14005c06d  mov     [rsp+98h+var_70], r14; void *
0x14005c072  mov     cl, 0A1h; int
0x14005c074  mov     byte ptr [rsp+98h+var_78], r13b; int
0x14005c079  call    SubmitControlRequest
0x14005c07e  mov     edi, eax
0x14005c080  test    eax, eax
0x14005c082  js      loc_14005C12E
0x14005c088  test    byte ptr [rbp+4F3h], 2
0x14005c08f  jz      short loc_14005C0CF
0x14005c091  mov     [rsp+98h+var_58], rbp; __int64
0x14005c096  mov     r8d, 900h; int
0x14005c09c  mov     [rsp+98h+var_60], r15; __int64
0x14005c0a1  mov     r9b, r12b; int
0x14005c0a4  mov     dword ptr [rsp+98h+Size], 4; Size
0x14005c0ac  mov     dl, 1; int
0x14005c0ae  mov     [rsp+98h+var_70], r14; void *
0x14005c0b3  mov     cl, 21h ; '!'; int
0x14005c0b5  mov     byte ptr [rsp+98h+var_78], r13b; int
0x14005c0ba  mov     dword ptr [rbp+520h], 1
0x14005c0c4  call    SubmitControlRequest
0x14005c0c9  mov     edi, eax
0x14005c0cb  test    eax, eax
0x14005c0cd  js      short loc_14005C12E
0x14005c0cf  mov     ecx, [r14]
0x14005c0d2  mov     edx, 1
0x14005c0d7  mov     eax, [rbx+4]
0x14005c0da  mov     [rbx], edx
0x14005c0dc  mov     [rbx+4], eax
0x14005c0df  shl     ecx, 0Ah
0x14005c0e2  lea     ebp, [rdx+27h]
0x14005c0e5  mov     [rbx+8], rbp
0x14005c0e9  xor     eax, eax
0x14005c0eb  mov     [rbx+10h], rdx
0x14005c0ef  mov     [rbx+18h], rax
0x14005c0f3  mov     [rbx+20h], eax
0x14005c0f6  mov     [rbx+24h], ecx
0x14005c0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c100  lea     rbx, WPP_GLOBAL_Control
0x14005c107  cmp     rcx, rbx
0x14005c10a  jz      short loc_14005C128
0x14005c10c  cmp     byte ptr [rcx+29h], 4
0x14005c110  jb      short loc_14005C128
0x14005c112  mov     r9d, [r14]
0x14005c115  lea     edx, [rbp+75h]
0x14005c118  mov     rcx, [rcx+18h]
0x14005c11c  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c123  call    WPP_SF_d
0x14005c128  mov     [rsi+38h], rbp
0x14005c12c  jmp     short loc_14005C185
0x14005c12e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c135  lea     rbx, WPP_GLOBAL_Control
0x14005c13c  cmp     rcx, rbx
0x14005c13f  jz      short loc_14005C1AF
0x14005c141  cmp     byte ptr [rcx+29h], 2
0x14005c145  jb      short loc_14005C185
0x14005c147  mov     edx, 9Eh
0x14005c14c  jmp     loc_14005C00E
0x14005c151  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c158  lea     rbx, WPP_GLOBAL_Control
0x14005c15f  mov     edi, 0C000000Dh
0x14005c164  cmp     rcx, rbx
0x14005c167  jz      short loc_14005C1AF
0x14005c169  cmp     byte ptr [rcx+29h], 2
0x14005c16d  jb      short loc_14005C185
0x14005c16f  mov     edx, 9Fh
0x14005c174  jmp     loc_14005C00E
0x14005c179  mov     edi, 0C0000001h
0x14005c17e  lea     rbx, WPP_GLOBAL_Control
0x14005c185  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c18c  cmp     rcx, rbx
0x14005c18f  jz      short loc_14005C1AF
0x14005c191  cmp     byte ptr [rcx+29h], 4
0x14005c195  jb      short loc_14005C1AF
0x14005c197  mov     rcx, [rcx+18h]
0x14005c19b  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c1a2  mov     edx, 0A0h
0x14005c1a7  mov     r9d, edi
0x14005c1aa  call    WPP_SF_d
0x14005c1af  mov     [rsi+30h], edi
0x14005c1b2  mov     eax, edi
0x14005c1b4  add     rsp, 58h
0x14005c1b8  pop     r15
0x14005c1ba  pop     r14
0x14005c1bc  pop     r13
0x14005c1be  pop     r12
0x14005c1c0  pop     rdi
0x14005c1c1  pop     rsi
0x14005c1c2  pop     rbp
0x14005c1c3  pop     rbx
0x14005c1c4  retn
```
