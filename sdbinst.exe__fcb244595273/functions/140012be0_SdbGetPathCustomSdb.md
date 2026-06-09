# SdbGetPathCustomSdb

- ea: `0x140012be0`
- end: `0x140012ca2`
- name: `SdbGetPathCustomSdb`
- size: `194`
- prototype: `_BOOL8 __fastcall(int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140004694`

## callees

- `0x14001008c`
- `0x140012be0`
- `0x140012d20`
- `0x140013638`
- `0x14002e3e2`
- `0x14002e420`

## string_xrefs

- `0x140012c69`: `SdbpGetSystemSdbFilePath failed [%x]`
- `0x140012c3a`: `SdbGetPathCustomSdb`

## pseudocode

```c
_BOOL8 __fastcall SdbGetPathCustomSdb(int a1, __int64 a2, __int64 a3)
{
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  int SystemSdbFilePath; // eax
  int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  __int64 v13; // [rsp+20h] [rbp-88h]
  unsigned __int16 v14[48]; // [rsp+30h] [rbp-78h] BYREF

  memset_0(v14, 0, 0x56u);
  if ( a3 && (SystemSdbFilePath = SdbpGetCustomSdbFileName(v14), v9 = SystemSdbFilePath, SystemSdbFilePath < 0) )
  {
    v10 = "SdbpGetCustomSdbFileName failed [%x]";
    v11 = 1620;
  }
  else
  {
    SystemSdbFilePath = SdbpGetSystemSdbFilePath(a1, v5, v6, v7, (__int64)v14);
    v9 = SystemSdbFilePath;
    if ( SystemSdbFilePath >= 0 )
    {
      v9 = 0;
      return v9 >= 0;
    }
    v10 = "SdbpGetSystemSdbFilePath failed [%x]";
    v11 = 1632;
  }
  LODWORD(v13) = SystemSdbFilePath;
  AslLogCallPrintf(1, "SdbGetPathCustomSdb", v11, v10, v13);
  return v9 >= 0;
}

```

## disassembly

```asm
0x140012be0  mov     [rsp+arg_8], rbx
0x140012be5  push    rdi
0x140012be6  sub     rsp, 0A0h
0x140012bed  mov     rax, cs:__security_cookie
0x140012bf4  xor     rax, rsp
0x140012bf7  mov     [rsp+0A8h+var_18], rax
0x140012bff  xor     edx, edx; Val
0x140012c01  mov     rbx, r8
0x140012c04  mov     rdi, rcx
0x140012c07  lea     rcx, [rsp+0A8h+var_78]; void *
0x140012c0c  lea     r8d, [rdx+56h]; Size
0x140012c10  call    memset_0
0x140012c15  test    rbx, rbx
0x140012c18  jz      short loc_140012C51
0x140012c1a  mov     r8, rbx
0x140012c1d  lea     rcx, [rsp+0A8h+var_78]; unsigned __int16 *
0x140012c22  call    SdbpGetCustomSdbFileName
0x140012c27  mov     ebx, eax
0x140012c29  test    eax, eax
0x140012c2b  jns     short loc_140012C51
0x140012c2d  lea     r9, aSdbpgetcustoms_0; "SdbpGetCustomSdbFileName failed [%x]"
0x140012c34  mov     r8d, 654h
0x140012c3a  lea     rdx, aSdbgetpathcust; "SdbGetPathCustomSdb"
0x140012c41  mov     dword ptr [rsp+0A8h+var_88], eax
0x140012c45  mov     ecx, 1
0x140012c4a  call    AslLogCallPrintf
0x140012c4f  jmp     short loc_140012C7A
0x140012c51  lea     rax, [rsp+0A8h+var_78]
0x140012c56  mov     rcx, rdi
0x140012c59  mov     [rsp+0A8h+var_88], rax
0x140012c5e  call    SdbpGetSystemSdbFilePath
0x140012c63  mov     ebx, eax
0x140012c65  test    eax, eax
0x140012c67  jns     short loc_140012C78
0x140012c69  lea     r9, aSdbpgetsystems; "SdbpGetSystemSdbFilePath failed [%x]"
0x140012c70  mov     r8d, 660h
0x140012c76  jmp     short loc_140012C3A
0x140012c78  xor     ebx, ebx
0x140012c7a  not     ebx
0x140012c7c  shr     ebx, 1Fh
0x140012c7f  mov     eax, ebx
0x140012c81  mov     rcx, [rsp+0A8h+var_18]
0x140012c89  xor     rcx, rsp; StackCookie
0x140012c8c  call    __security_check_cookie
0x140012c91  mov     rbx, [rsp+0A8h+arg_8]
0x140012c99  add     rsp, 0A0h
0x140012ca0  pop     rdi
0x140012ca1  retn
```
