# NtProcessStartupW_AfterSecurityCookieInitialized

- ea: `0x140005c00`
- end: `0x140005f5d`
- name: `NtProcessStartupW_AfterSecurityCookieInitialized`
- size: `861`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140005be0`

## callees

- `0x140005c00`
- `0x140005f64`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140005cf9`
- `ntdll!RtlAllocateHeap` at `0x140005cf9`
- `ntdll!NtTerminateProcess` at `0x140005da1`
- `ntdll!RtlNormalizeProcessParams` at `0x140005c18`
- `ntdll!RtlNormalizeProcessParams` at `0x140005c18`
- `ntdll!iswspace` at `0x140005e1a`
- `ntdll!iswspace` at `0x140005e71`
- `ntdll!iswspace` at `0x140005ed0`
- `ntdll!iswspace` at `0x140005f03`
- `ntdll!iswspace` at `0x140005e1a`
- `ntdll!iswspace` at `0x140005e71`
- `ntdll!iswspace` at `0x140005ed0`
- `ntdll!iswspace` at `0x140005f03`

## pseudocode

```c
NTSTATUS __fastcall NtProcessStartupW_AfterSecurityCookieInitialized(__int64 a1)
{
  PRTL_USER_PROCESS_PARAMETERS v2; // r13
  PCWSTR *v3; // rcx
  int v4; // eax
  __int64 DebugFlags; // r8
  unsigned int v6; // ebp
  __int64 v7; // rsi
  UNICODE_STRING *p_CommandLine; // rdi
  wint_t *Buffer; // r14
  int Length; // r15d
  PWSTR Environment; // rax
  int v12; // edx
  __int64 v14; // rax
  __int64 v15; // rbx
  SIZE_T v16; // rsi
  char **Heap; // rax
  char **v18; // rdi
  _QWORD *v19; // rdi
  PWSTR v20; // rcx
  NTSTATUS v21; // eax
  char *v24; // rbx
  char *v25; // rbp
  char *v26; // rsi
  wint_t *v27; // rbx
  _QWORD v28[3]; // [rsp+20h] [rbp-58h] BYREF
  ULONG v29; // [rsp+80h] [rbp+8h]
  int v30; // [rsp+88h] [rbp+10h]
  PCWSTR *v31; // [rsp+98h] [rbp+20h]

  v28[0] = 0;
  v2 = RtlNormalizeProcessParams(*(PRTL_USER_PROCESS_PARAMETERS *)(a1 + 32));
  v3 = (PCWSTR *)v28;
  v4 = 0;
  v31 = (PCWSTR *)v28;
  v30 = 0;
  if ( !v2 )
  {
    DebugFlags = 0;
    goto LABEL_21;
  }
  DebugFlags = v2->DebugFlags;
  v6 = 1;
  v7 = 0;
  p_CommandLine = &v2->CommandLine;
  v29 = v2->DebugFlags;
  if ( v2->CommandLine.Buffer && p_CommandLine->Length
    || (Buffer = 0, p_CommandLine = &v2->ImagePathName, Length = 0, v2->ImagePathName.Buffer) )
  {
    Length = p_CommandLine->Length;
    Buffer = p_CommandLine->Buffer;
    if ( p_CommandLine->Length )
    {
      do
      {
        if ( !*Buffer || !Length )
          break;
        while ( *Buffer )
        {
          if ( iswspace(*Buffer) )
          {
            ++Buffer;
            Length -= 2;
            if ( Length )
              continue;
          }
          if ( !Length )
            goto LABEL_59;
          break;
        }
        if ( *Buffer )
        {
          ++v6;
          v27 = Buffer;
          do
          {
            ++Buffer;
            Length -= 2;
          }
          while ( Length && !iswspace(*Buffer) );
          v7 += 2 * (Buffer - v27) + 2;
        }
      }
      while ( Length );
LABEL_59:
      DebugFlags = v29;
    }
  }
  Environment = v2->Environment;
  v12 = 0;
  if ( Environment && *Environment )
  {
    do
    {
      ++Environment;
      ++v12;
      while ( *Environment++ )
        ;
    }
    while ( *Environment );
  }
  v14 = v6 + v12 + 1;
  if ( (unsigned int)v14 <= 2 )
    goto LABEL_16;
  if ( v6 > 1 )
  {
    Buffer = p_CommandLine->Buffer;
    Length = p_CommandLine->Length;
  }
  v15 = v14;
  v16 = 8 * v14 + v7;
  Heap = (char **)RtlAllocateHeap(*(PVOID *)(a1 + 48), 0, v16);
  v18 = Heap;
  if ( Heap )
  {
    v31 = (PCWSTR *)Heap;
    if ( v6 > 1 )
    {
      v24 = (char *)&Heap[v15];
      v25 = (char *)Heap + v16;
      while ( Length )
      {
        if ( v24 >= v25 || !*Buffer )
          break;
        while ( *Buffer )
        {
          if ( iswspace(*Buffer) )
          {
            ++Buffer;
            Length -= 2;
            if ( Length )
              continue;
          }
          if ( !Length )
            goto LABEL_14;
          break;
        }
        if ( *Buffer )
        {
          *v18++ = v24;
          ++v30;
          do
          {
            v26 = v24;
            *(_WORD *)v24 = *Buffer++;
            v24 += 2;
            Length -= 2;
            if ( !Length )
              break;
            if ( v24 >= v25 )
              goto LABEL_42;
          }
          while ( !iswspace(*Buffer) );
          if ( v24 < v25 )
          {
            *(_WORD *)v24 = 0;
            v24 += 2;
            continue;
          }
LABEL_42:
          v24 = v26;
          *(_WORD *)v26 = 0;
        }
      }
    }
LABEL_14:
    DebugFlags = v29;
    *v18 = 0;
    v19 = v18 + 1;
    v20 = v2->Environment;
    if ( v20 && *v20 )
    {
      do
      {
        *v19++ = v20++;
        while ( *v20++ )
          ;
      }
      while ( *v20 );
    }
    *v19 = 0;
LABEL_16:
    v21 = 0;
    goto LABEL_17;
  }
  DebugFlags = v29;
  v21 = -1073741801;
LABEL_17:
  if ( (_DWORD)DebugFlags )
    __debugbreak();
  if ( v21 >= 0 )
  {
    v4 = v30;
    v3 = v31;
LABEL_21:
    v21 = wmain(v4, v3, DebugFlags, DebugFlags);
  }
  return NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, v21);
}

```

## disassembly

```asm
0x140005c00  push    r12
0x140005c02  push    r13
0x140005c04  sub     rsp, 68h
0x140005c08  mov     r12, rcx
0x140005c0b  mov     [rsp+78h+var_58], 0
0x140005c14  mov     rcx, [rcx+20h]; ProcessParameters
0x140005c18  call    cs:__imp_RtlNormalizeProcessParams
0x140005c1e  mov     r13, rax
0x140005c21  lea     rcx, [rsp+78h+var_58]
0x140005c26  xor     eax, eax
0x140005c28  mov     [rsp+78h+arg_18], rcx
0x140005c30  mov     [rsp+78h+arg_8], eax
0x140005c37  test    r13, r13
0x140005c3a  jz      loc_140005F55
0x140005c40  mov     r8d, [r13+0Ch]
0x140005c44  mov     [rsp+78h+var_20], rbp
0x140005c49  mov     ebp, 1
0x140005c4e  mov     [rsp+78h+var_28], rsi
0x140005c53  xor     esi, esi
0x140005c55  mov     [rsp+78h+var_30], rdi
0x140005c5a  lea     rdi, [r13+70h]
0x140005c5e  mov     [rsp+78h+var_18], rbx
0x140005c63  mov     [rsp+78h+var_38], r14
0x140005c68  mov     [rsp+78h+var_40], r15
0x140005c6d  mov     [rsp+78h+arg_10], eax
0x140005c74  mov     [rsp+78h+arg_0], r8d
0x140005c7c  cmp     [rdi+8], rax
0x140005c80  jnz     loc_140005EA1
0x140005c86  xor     r14d, r14d
0x140005c89  lea     rdi, [r13+60h]
0x140005c8d  xor     r15d, r15d
0x140005c90  cmp     [rdi+8], rax
0x140005c94  jnz     loc_140005EAA
0x140005c9a  mov     rax, [r13+80h]
0x140005ca1  xor     edx, edx
0x140005ca3  test    rax, rax
0x140005ca6  jz      short loc_140005CD1
0x140005ca8  cmp     [rax], dx
0x140005cab  jz      short loc_140005CD1
0x140005cad  nop     dword ptr [rax]
0x140005cb0  add     rax, 2
0x140005cb4  inc     edx
0x140005cb6  nop     word ptr [rax+rax+00000000h]
0x140005cc0  movzx   ecx, word ptr [rax]
0x140005cc3  add     rax, 2
0x140005cc7  test    cx, cx
0x140005cca  jnz     short loc_140005CC0
0x140005ccc  cmp     [rax], cx
0x140005ccf  jnz     short loc_140005CB0
0x140005cd1  lea     eax, [rdx+1]
0x140005cd4  add     eax, ebp
0x140005cd6  cmp     eax, 2
0x140005cd9  jbe     short loc_140005D42
0x140005cdb  cmp     ebp, 1
0x140005cde  ja      loc_140005F30
0x140005ce4  mov     rcx, [r12+30h]; HeapHandle
0x140005ce9  lea     rbx, ds:0[rax*8]
0x140005cf1  add     rsi, rbx
0x140005cf4  xor     edx, edx; Flags
0x140005cf6  mov     r8, rsi; Size
0x140005cf9  call    cs:__imp_RtlAllocateHeap
0x140005cff  mov     rdi, rax
0x140005d02  test    rax, rax
0x140005d05  jz      loc_140005F3D
0x140005d0b  mov     [rsp+78h+arg_18], rax
0x140005d13  cmp     ebp, 1
0x140005d16  ja      loc_140005DD6
0x140005d1c  mov     r8d, [rsp+78h+arg_0]
0x140005d24  mov     qword ptr [rdi], 0
0x140005d2b  add     rdi, 8
0x140005d2f  mov     rcx, [r13+80h]
0x140005d36  test    rcx, rcx
0x140005d39  jnz     short loc_140005DA8
0x140005d3b  mov     qword ptr [rdi], 0
0x140005d42  mov     eax, [rsp+78h+arg_10]
0x140005d49  mov     r15, [rsp+78h+var_40]
0x140005d4e  mov     r14, [rsp+78h+var_38]
0x140005d53  mov     rdi, [rsp+78h+var_30]
0x140005d58  mov     rsi, [rsp+78h+var_28]
0x140005d5d  mov     rbp, [rsp+78h+var_20]
0x140005d62  mov     rbx, [rsp+78h+var_18]
0x140005d67  test    r8d, r8d
0x140005d6a  jnz     loc_140005F4F
0x140005d70  test    eax, eax
0x140005d72  js      short loc_140005D90
0x140005d74  mov     eax, [rsp+78h+arg_8]
0x140005d7b  mov     rcx, [rsp+78h+arg_18]
0x140005d83  mov     rdx, rcx
0x140005d86  mov     r9d, r8d
0x140005d89  mov     ecx, eax
0x140005d8b  call    wmain
0x140005d90  mov     edx, eax
0x140005d92  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140005d99  add     rsp, 68h
0x140005d9d  pop     r13
0x140005d9f  pop     r12
0x140005da1  jmp     cs:__imp_NtTerminateProcess
0x140005da8  cmp     word ptr [rcx], 0
0x140005dac  jz      short loc_140005D3B
0x140005dae  xchg    ax, ax
0x140005db0  mov     [rdi], rcx
0x140005db3  add     rdi, 8
0x140005db7  add     rcx, 2
0x140005dbb  nop     dword ptr [rax+rax+00h]
0x140005dc0  movzx   eax, word ptr [rcx]
0x140005dc3  add     rcx, 2
0x140005dc7  test    ax, ax
0x140005dca  jnz     short loc_140005DC0
0x140005dcc  cmp     [rcx], ax
0x140005dcf  jnz     short loc_140005DB0
0x140005dd1  jmp     loc_140005D3B
0x140005dd6  add     rbx, rax
0x140005dd9  lea     rbp, [rsi+rax]
0x140005ddd  test    r15d, r15d
0x140005de0  jz      loc_140005D1C
0x140005de6  mov     eax, [rsp+78h+arg_0]
0x140005ded  mov     [rsp+78h+arg_0], eax
0x140005df4  cmp     rbx, rbp
0x140005df7  jnb     loc_140005D1C
0x140005dfd  cmp     word ptr [r14], 0
0x140005e02  jz      loc_140005D1C
0x140005e08  test    r15d, r15d
0x140005e0b  jz      loc_140005D1C
0x140005e11  movzx   ecx, word ptr [r14]; C
0x140005e15  test    cx, cx
0x140005e18  jz      short loc_140005E37
0x140005e1a  call    cs:__imp_iswspace
0x140005e20  test    eax, eax
0x140005e22  jz      short loc_140005E2E
0x140005e24  add     r14, 2
0x140005e28  add     r15d, 0FFFFFFFEh
0x140005e2c  jnz     short loc_140005E11
0x140005e2e  test    r15d, r15d
0x140005e31  jz      loc_140005D1C
0x140005e37  cmp     word ptr [r14], 0
0x140005e3c  jz      short loc_140005E93
0x140005e3e  mov     [rdi], rbx
0x140005e41  add     rdi, 8
0x140005e45  inc     [rsp+78h+arg_8]
0x140005e4c  nop     dword ptr [rax+00h]
0x140005e50  movzx   eax, word ptr [r14]
0x140005e54  mov     rsi, rbx
0x140005e57  mov     [rbx], ax
0x140005e5a  add     r14, 2
0x140005e5e  add     rbx, 2
0x140005e62  add     r15d, 0FFFFFFFEh
0x140005e66  jz      short loc_140005E7B
0x140005e68  cmp     rbx, rbp
0x140005e6b  jnb     short loc_140005E8B
0x140005e6d  movzx   ecx, word ptr [r14]; C
0x140005e71  call    cs:__imp_iswspace
0x140005e77  test    eax, eax
0x140005e79  jz      short loc_140005E50
0x140005e7b  cmp     rbx, rbp
0x140005e7e  jnb     short loc_140005E8B
0x140005e80  xor     eax, eax
0x140005e82  mov     [rbx], ax
0x140005e85  add     rbx, 2
0x140005e89  jmp     short loc_140005E93
0x140005e8b  xor     eax, eax
0x140005e8d  mov     rbx, rsi
0x140005e90  mov     [rsi], ax
0x140005e93  test    r15d, r15d
0x140005e96  jz      loc_140005D1C
0x140005e9c  jmp     loc_140005DF4
0x140005ea1  cmp     [rdi], ax
0x140005ea4  jz      loc_140005C86
0x140005eaa  movzx   r15d, word ptr [rdi]
0x140005eae  mov     r14, [rdi+8]
0x140005eb2  test    r15d, r15d
0x140005eb5  jz      loc_140005C9A
0x140005ebb  cmp     word ptr [r14], 0
0x140005ec0  jz      short loc_140005F23
0x140005ec2  test    r15d, r15d
0x140005ec5  jz      short loc_140005F23
0x140005ec7  movzx   ecx, word ptr [r14]; C
0x140005ecb  test    cx, cx
0x140005ece  jz      short loc_140005EE9
0x140005ed0  call    cs:__imp_iswspace
0x140005ed6  test    eax, eax
0x140005ed8  jz      short loc_140005EE4
0x140005eda  add     r14, 2
0x140005ede  add     r15d, 0FFFFFFFEh
0x140005ee2  jnz     short loc_140005EC7
0x140005ee4  test    r15d, r15d
0x140005ee7  jz      short loc_140005F23
0x140005ee9  cmp     word ptr [r14], 0
0x140005eee  jz      short loc_140005F1E
0x140005ef0  inc     ebp
0x140005ef2  mov     rbx, r14
0x140005ef5  add     r14, 2
0x140005ef9  add     r15d, 0FFFFFFFEh
0x140005efd  jz      short loc_140005F0D
0x140005eff  movzx   ecx, word ptr [r14]; C
0x140005f03  call    cs:__imp_iswspace
0x140005f09  test    eax, eax
0x140005f0b  jz      short loc_140005EF5
0x140005f0d  mov     rax, r14
0x140005f10  sub     rax, rbx
0x140005f13  sar     rax, 1
0x140005f16  lea     rsi, [rsi+rax*2]
0x140005f1a  add     rsi, 2
0x140005f1e  test    r15d, r15d
0x140005f21  jnz     short loc_140005EBB
0x140005f23  mov     r8d, [rsp+78h+arg_0]
0x140005f2b  jmp     loc_140005C9A
0x140005f30  mov     r14, [rdi+8]
0x140005f34  movzx   r15d, word ptr [rdi]
0x140005f38  jmp     loc_140005CE4
0x140005f3d  mov     r8d, [rsp+78h+arg_0]
0x140005f45  mov     eax, 0C0000017h
0x140005f4a  jmp     loc_140005D49
0x140005f4f  int     3; Trap to Debugger
0x140005f50  jmp     loc_140005D70
0x140005f55  xor     r8d, r8d
0x140005f58  jmp     loc_140005D83
```
