# AslPathToSystemPath

- ea: `0x14001031c`
- end: `0x1400103cf`
- name: `AslPathToSystemPath`
- size: `179`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001687c`

## callees

- `0x14001008c`
- `0x14001031c`
- `0x1400103d8`
- `0x140010d44`
- `0x14002e420`

## string_xrefs

- `0x140010364`: `AslPathToSystemPathBuf failed [%x]`
- `0x140010371`: `AslPathToSystemPath`
- `0x14001039b`: `Failed to allocate path string [%x]`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPath(_QWORD *a1, unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  int v8; // [rsp+20h] [rbp-238h]
  unsigned __int16 v9[264]; // [rsp+30h] [rbp-228h] BYREF

  *a1 = 0;
  v9[0] = 0;
  v3 = AslPathToSystemPathBuf(v9, 0x104u, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v3 = AslStringDuplicate(a1, v9);
    v4 = v3;
    if ( v3 >= 0 )
      return 0;
    v5 = "Failed to allocate path string [%x]";
    v6 = 1543;
  }
  else
  {
    v5 = "AslPathToSystemPathBuf failed [%x]";
    v6 = 1537;
  }
  v8 = v3;
  AslLogCallPrintf(1, "AslPathToSystemPath", v6, v5, v8);
  return v4;
}

```

## disassembly

```asm
0x14001031c  mov     [rsp+arg_10], rbx
0x140010321  push    rdi
0x140010322  sub     rsp, 250h
0x140010329  mov     rax, cs:__security_cookie
0x140010330  xor     rax, rsp
0x140010333  mov     [rsp+258h+var_18], rax
0x14001033b  mov     rdi, rcx
0x14001033e  mov     qword ptr [rcx], 0
0x140010345  xor     eax, eax
0x140010347  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x14001034c  mov     r8, rdx; unsigned __int16 *
0x14001034f  mov     [rsp+258h+var_228], ax
0x140010354  mov     edx, 104h; unsigned __int64
0x140010359  call    AslPathToSystemPathBuf
0x14001035e  mov     ebx, eax
0x140010360  test    eax, eax
0x140010362  jns     short loc_140010388
0x140010364  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x14001036b  mov     r8d, 601h
0x140010371  lea     rdx, aAslpathtosyste_1; "AslPathToSystemPath"
0x140010378  mov     [rsp+258h+var_238], eax
0x14001037c  mov     ecx, 1
0x140010381  call    AslLogCallPrintf
0x140010386  jmp     short loc_1400103AC
0x140010388  lea     rdx, [rsp+258h+var_228]
0x14001038d  mov     rcx, rdi
0x140010390  call    AslStringDuplicate
0x140010395  mov     ebx, eax
0x140010397  test    eax, eax
0x140010399  jns     short loc_1400103AA
0x14001039b  lea     r9, aFailedToAlloca_3; "Failed to allocate path string [%x]"
0x1400103a2  mov     r8d, 607h
0x1400103a8  jmp     short loc_140010371
0x1400103aa  xor     ebx, ebx
0x1400103ac  mov     eax, ebx
0x1400103ae  mov     rcx, [rsp+258h+var_18]
0x1400103b6  xor     rcx, rsp; StackCookie
0x1400103b9  call    __security_check_cookie
0x1400103be  mov     rbx, [rsp+258h+arg_10]
0x1400103c6  add     rsp, 250h
0x1400103cd  pop     rdi
0x1400103ce  retn
```
