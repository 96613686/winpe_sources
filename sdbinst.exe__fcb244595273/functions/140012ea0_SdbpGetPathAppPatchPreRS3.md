# SdbpGetPathAppPatchPreRS3

- ea: `0x140012ea0`
- end: `0x140013054`
- name: `SdbpGetPathAppPatchPreRS3`
- size: `436`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x14001008c`
- `0x1400100c4`
- `0x140012db0`
- `0x140012ea0`
- `0x14001357c`
- `0x14002e420`

## string_xrefs

- `0x14001300a`: `AslPathCombine failed [%x]`
- `0x140012f42`: `SdbpGetPathAppPatchPreRS3`
- `0x140012fcc`: `RtlStringCchCopyW failed to copy FileName [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetPathAppPatchPreRS3(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  int ProcessHostGuestArchitectures; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  __int64 v12; // rax
  unsigned __int16 *v13; // rdx
  __int64 v14; // r9
  unsigned __int16 *v15; // rcx
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  __int16 v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v19; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v20[22]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v21[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_OWORD *)v20 = *(_OWORD *)L"AppPatch64";
  *(_QWORD *)&v20[14] = *(_QWORD *)L"h64";
  if ( a2 < 0xB )
    return 3221225507LL;
  v19 = -1;
  v21[0] = 0;
  v18[0] = -1;
  ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(&v19, v18, a4);
  v9 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures < 0 )
  {
    v10 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
    v11 = 1006;
LABEL_5:
    v16 = ProcessHostGuestArchitectures;
    AslLogCallPrintf(1, "SdbpGetPathAppPatchPreRS3", v11, v10, v16);
    return v9;
  }
  if ( v18[0] == 9 || v18[0] == 12 )
  {
    if ( !a3 )
      a3 = (unsigned __int16 *)&Format;
    ProcessHostGuestArchitectures = AslPathCombine(v20, a3, v21, 260);
    v9 = ProcessHostGuestArchitectures;
    if ( ProcessHostGuestArchitectures < 0 )
    {
      v10 = "AslPathCombine failed [%x]";
      v11 = 1018;
      goto LABEL_5;
    }
    return (unsigned int)SdbpGetPathAppPatch(a1, a2, v21);
  }
  v12 = 2147483646;
  v13 = v21;
  if ( !a3 )
    a3 = (unsigned __int16 *)&Format;
  v14 = 260;
  do
  {
    if ( !v12 )
      break;
    if ( !*a3 )
      break;
    *v13++ = *a3++;
    --v12;
    --v14;
  }
  while ( v14 );
  v15 = v13 - 1;
  v9 = v14 == 0 ? 0x80000005 : 0;
  if ( v14 )
    v15 = v13;
  *v15 = 0;
  if ( v14 )
    return (unsigned int)SdbpGetPathAppPatch(a1, a2, v21);
  v17 = -2147483643;
  AslLogCallPrintf(1, "SdbpGetPathAppPatchPreRS3", 1024, "RtlStringCchCopyW failed to copy FileName [%x]", v17);
  return v9;
}

```

## disassembly

```asm
0x140012ea0  push    rbp
0x140012ea2  push    rbx
0x140012ea3  push    rsi
0x140012ea4  push    rdi
0x140012ea5  push    r12
0x140012ea7  push    r14
0x140012ea9  push    r15
0x140012eab  lea     rbp, [rsp-170h]
0x140012eb3  sub     rsp, 270h
0x140012eba  mov     rax, cs:__security_cookie
0x140012ec1  xor     rax, rsp
0x140012ec4  mov     [rbp+1A0h+var_40], rax
0x140012ecb  movsd   xmm1, qword ptr cs:aApppatch64+0Eh; "h64"
0x140012ed3  mov     rsi, r9
0x140012ed6  mov     rdi, r8
0x140012ed9  mov     r14, rdx
0x140012edc  mov     r15, rcx
0x140012edf  movups  xmm0, xmmword ptr cs:aApppatch64; "AppPatch64"
0x140012ee6  movups  xmmword ptr [rsp+2A0h+var_268], xmm0
0x140012eeb  movsd   qword ptr [rsp+2A0h+var_268+0Eh], xmm1
0x140012ef1  cmp     rdx, 0Bh
0x140012ef5  jnb     short loc_140012F01
0x140012ef7  mov     eax, 0C0000023h
0x140012efc  jmp     loc_140013033
0x140012f01  mov     eax, 0FFFFh
0x140012f06  lea     rdx, [rsp+2A0h+var_270]
0x140012f0b  xor     r12d, r12d
0x140012f0e  mov     [rsp+2A0h+var_26C], ax
0x140012f13  mov     r8, rsi
0x140012f16  mov     [rsp+2A0h+var_250], r12w
0x140012f1c  lea     rcx, [rsp+2A0h+var_26C]
0x140012f21  mov     [rsp+2A0h+var_270], ax
0x140012f26  call    SdbpGetProcessHostGuestArchitectures
0x140012f2b  mov     ebx, eax
0x140012f2d  test    eax, eax
0x140012f2f  jns     short loc_140012F58
0x140012f31  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x140012f38  mov     r8d, 3EEh
0x140012f3e  mov     [rsp+2A0h+var_280], eax
0x140012f42  lea     rdx, aSdbpgetpathapp; "SdbpGetPathAppPatchPreRS3"
0x140012f49  mov     ecx, 1
0x140012f4e  call    AslLogCallPrintf
0x140012f53  jmp     loc_140013031
0x140012f58  cmp     [rsp+2A0h+var_270], 9
0x140012f5e  jz      short loc_140012FDE
0x140012f60  cmp     [rsp+2A0h+var_270], 0Ch
0x140012f66  jz      short loc_140012FDE
0x140012f68  test    rdi, rdi
0x140012f6b  lea     rcx, Format
0x140012f72  mov     eax, 7FFFFFFEh
0x140012f77  lea     rdx, [rsp+2A0h+var_250]
0x140012f7c  cmovz   rdi, rcx
0x140012f80  mov     r9d, 104h
0x140012f86  test    rax, rax
0x140012f89  jz      short loc_140012FA7
0x140012f8b  movzx   ecx, word ptr [rdi]
0x140012f8e  test    cx, cx
0x140012f91  jz      short loc_140012FA7
0x140012f93  mov     [rdx], cx
0x140012f96  add     rdi, 2
0x140012f9a  add     rdx, 2
0x140012f9e  dec     rax
0x140012fa1  sub     r9, 1
0x140012fa5  jnz     short loc_140012F86
0x140012fa7  mov     rax, r9
0x140012faa  lea     rcx, [rdx-2]
0x140012fae  neg     rax
0x140012fb1  sbb     ebx, ebx
0x140012fb3  not     ebx
0x140012fb5  and     ebx, 80000005h
0x140012fbb  test    r9, r9
0x140012fbe  cmovnz  rcx, rdx
0x140012fc2  mov     [rcx], r12w
0x140012fc6  jnz     short loc_14001301C
0x140012fc8  mov     [rsp+2A0h+var_280], ebx
0x140012fcc  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed to copy FileNa"...
0x140012fd3  mov     r8d, 400h
0x140012fd9  jmp     loc_140012F42
0x140012fde  lea     rcx, Format
0x140012fe5  test    rdi, rdi
0x140012fe8  mov     r9d, 104h
0x140012fee  lea     r8, [rsp+2A0h+var_250]
0x140012ff3  cmovz   rdi, rcx
0x140012ff7  lea     rcx, [rsp+2A0h+var_268]
0x140012ffc  mov     rdx, rdi
0x140012fff  call    AslPathCombine
0x140013004  mov     ebx, eax
0x140013006  test    eax, eax
0x140013008  jns     short loc_14001301C
0x14001300a  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140013011  mov     r8d, 3FAh
0x140013017  jmp     loc_140012F3E
0x14001301c  mov     r9, rsi
0x14001301f  lea     r8, [rsp+2A0h+var_250]
0x140013024  mov     rdx, r14; unsigned __int64
0x140013027  mov     rcx, r15; unsigned __int16 *
0x14001302a  call    SdbpGetPathAppPatch
0x14001302f  mov     ebx, eax
0x140013031  mov     eax, ebx
0x140013033  mov     rcx, [rbp+1A0h+var_40]
0x14001303a  xor     rcx, rsp; StackCookie
0x14001303d  call    __security_check_cookie
0x140013042  add     rsp, 270h
0x140013049  pop     r15
0x14001304b  pop     r14
0x14001304d  pop     r12
0x14001304f  pop     rdi
0x140013050  pop     rsi
0x140013051  pop     rbx
0x140013052  pop     rbp
0x140013053  retn
```
