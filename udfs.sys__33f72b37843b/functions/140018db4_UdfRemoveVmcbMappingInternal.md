# UdfRemoveVmcbMappingInternal

- ea: `0x140018db4`
- end: `0x140018f23`
- name: `UdfRemoveVmcbMappingInternal`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140018ff8`

## callees

- `0x140010990`
- `0x140018db4`
- `0x1400192c8`
- `0x140056b54`

## import_xrefs

- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x140018eba`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x140018ed4`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x140018eba`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x140018ed4`

## pseudocode

```c
_DWORD *__fastcall UdfRemoveVmcbMappingInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _DWORD *a6)
{
  int v8; // r14d
  unsigned int v9; // edi
  unsigned int v10; // r12d
  unsigned int v11; // esi
  _DWORD *result; // rax
  char v13; // [rsp+28h] [rbp-50h]
  unsigned int Vbn; // [rsp+30h] [rbp-48h] BYREF
  unsigned int Vbn_4; // [rsp+34h] [rbp-44h]
  int v16; // [rsp+38h] [rbp-40h]
  unsigned int v17; // [rsp+80h] [rbp+8h] BYREF
  int v18; // [rsp+84h] [rbp+Ch]
  int v19; // [rsp+90h] [rbp+18h]

  v19 = a3;
  v18 = HIDWORD(a1);
  Vbn = 0;
  v17 = 0;
  v8 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
  {
    v13 = 89;
    WPP_SF_DDc(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), a2, a3, (unsigned int)a3, a4, v13, Vbn);
    LODWORD(a3) = v19;
  }
  v9 = 0;
  Vbn_4 = 0;
  while ( v9 < a4 )
  {
    v10 = v9 + a3;
    if ( (unsigned __int8)UdfVmcbLookupMcbEntry(a2 + 216, v9 + (unsigned int)a3, &Vbn, &v17) )
    {
      v11 = v17;
      if ( v17 > a4 - v9 )
        v11 = a4 - v9;
      v17 = v11;
      v8 += v11;
      v16 = v8;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
      {
        WPP_SF_DDD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          33,
          WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids,
          v10,
          Vbn,
          v11);
      }
      FsRtlRemoveLargeMcbEntry((PLARGE_MCB)(a2 + 216), v10, v11);
      FsRtlRemoveLargeMcbEntry((PLARGE_MCB)(a2 + 248), Vbn, v11);
      v9 = v11 + v9 - 1;
      Vbn_4 = v9;
    }
    Vbn_4 = ++v9;
    LODWORD(a3) = v19;
  }
  result = a6;
  if ( a6 )
    *a6 = v8;
  return result;
}

```

## disassembly

```asm
0x140018db4  mov     rax, rsp
0x140018db7  mov     [rax+18h], r8d
0x140018dbb  mov     [rax+8], rcx
0x140018dbf  push    rbx
0x140018dc0  push    rsi
0x140018dc1  push    rdi
0x140018dc2  push    r12
0x140018dc4  push    r13
0x140018dc6  push    r14
0x140018dc8  push    r15
0x140018dca  sub     rsp, 40h
0x140018dce  mov     r15d, r9d
0x140018dd1  mov     r13, rdx
0x140018dd4  mov     dword ptr [rax-48h], 0
0x140018ddb  mov     dword ptr [rax+8], 0
0x140018de2  xor     r14d, r14d
0x140018de5  lea     rbx, WPP_GLOBAL_Control
0x140018dec  mov     rcx, cs:WPP_GLOBAL_Control
0x140018df3  cmp     rcx, rbx
0x140018df6  jz      short loc_140018E1D
0x140018df8  test    dword ptr [rcx+2Ch], 400000h
0x140018dff  jz      short loc_140018E1D
0x140018e01  mov     byte ptr [rax-50h], 59h ; 'Y'
0x140018e05  mov     [rax-58h], r9d
0x140018e09  mov     r9d, r8d
0x140018e0c  mov     rcx, [rcx+18h]
0x140018e10  call    WPP_SF_DDc
0x140018e15  mov     r8d, [rsp+78h+arg_10]
0x140018e1d  xor     edi, edi
0x140018e1f  mov     dword ptr [rsp+78h+Vbn+4], edi
0x140018e23  cmp     edi, r15d
0x140018e26  jnb     loc_140018F02
0x140018e2c  lea     r12d, [rdi+r8]
0x140018e30  lea     rcx, [r13+0D8h]
0x140018e37  lea     r9, [rsp+78h+arg_0]
0x140018e3f  lea     r8, [rsp+78h+Vbn]
0x140018e44  mov     edx, r12d
0x140018e47  call    UdfVmcbLookupMcbEntry
0x140018e4c  test    al, al
0x140018e4e  jz      loc_140018EEF
0x140018e54  mov     eax, r15d
0x140018e57  sub     eax, edi
0x140018e59  mov     esi, [rsp+78h+arg_0]
0x140018e60  cmp     esi, eax
0x140018e62  cmova   esi, eax
0x140018e65  mov     [rsp+78h+arg_0], esi
0x140018e6c  add     r14d, esi
0x140018e6f  mov     [rsp+78h+var_40], r14d
0x140018e74  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e7b  cmp     rcx, rbx
0x140018e7e  jz      short loc_140018EAD
0x140018e80  test    dword ptr [rcx+2Ch], 400000h
0x140018e87  jz      short loc_140018EAD
0x140018e89  mov     edx, 21h ; '!'
0x140018e8e  mov     dword ptr [rsp+78h+var_50], esi
0x140018e92  mov     eax, dword ptr [rsp+78h+Vbn]
0x140018e96  mov     [rsp+78h+var_58], eax
0x140018e9a  mov     r9d, r12d
0x140018e9d  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x140018ea4  mov     rcx, [rcx+18h]
0x140018ea8  call    WPP_SF_DDD
0x140018ead  mov     edx, r12d; Vbn
0x140018eb0  mov     r8d, esi; SectorCount
0x140018eb3  lea     rcx, [r13+0D8h]; Mcb
0x140018eba  call    cs:__imp_FsRtlRemoveLargeMcbEntry
0x140018ec1  nop     dword ptr [rax+rax+00h]
0x140018ec6  mov     edx, dword ptr [rsp+78h+Vbn]; Vbn
0x140018eca  lea     rcx, [r13+0F8h]; Mcb
0x140018ed1  mov     r8d, esi; SectorCount
0x140018ed4  call    cs:__imp_FsRtlRemoveLargeMcbEntry
0x140018edb  nop     dword ptr [rax+rax+00h]
0x140018ee0  dec     edi
0x140018ee2  add     edi, esi
0x140018ee4  mov     dword ptr [rsp+78h+Vbn+4], edi
0x140018ee8  lea     rbx, WPP_GLOBAL_Control
0x140018eef  inc     edi
0x140018ef1  mov     dword ptr [rsp+78h+Vbn+4], edi
0x140018ef5  mov     r8d, [rsp+78h+arg_10]
0x140018efd  jmp     loc_140018E23
0x140018f02  mov     rax, [rsp+78h+arg_28]
0x140018f0a  test    rax, rax
0x140018f0d  jz      short loc_140018F12
0x140018f0f  mov     [rax], r14d
0x140018f12  add     rsp, 40h
0x140018f16  pop     r15
0x140018f18  pop     r14
0x140018f1a  pop     r13
0x140018f1c  pop     r12
0x140018f1e  pop     rdi
0x140018f1f  pop     rsi
0x140018f20  pop     rbx
0x140018f21  retn
0x14001dfad  push    rbp
0x14001dfaf  sub     rsp, 30h
0x14001dfb3  mov     rbp, rdx
0x14001dfb6  add     rsp, 30h
0x14001dfba  pop     rbp
0x14001dfbb  retn
```
