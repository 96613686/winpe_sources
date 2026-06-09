# AddApiSetHostLoadRefCount

- ea: `0x1401444b8`
- end: `0x14014460e`
- name: `AddApiSetHostLoadRefCount`
- size: `342`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140144268`

## callees

- `0x1401444b8`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1401445c2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401445d1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401445c2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401445d1`
- `ntoskrnl!KeBugCheckEx` at `0x140144601`
- `ntoskrnl!KeBugCheckEx` at `0x140144601`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1401445e0`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1401445e0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140144526`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140144562`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14014457c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401445a4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140144526`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140144562`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14014457c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401445a4`
- `WIN32K!gSessionApiSetHostRefCount` at `0x140144548`

## string_xrefs

- `0x1401444d5`: `\SystemRoot\System32\win32k.sys`
- `0x1401444ec`: `\SystemRoot\System32\win32kbase.sys`
- `0x140144518`: `\SystemRoot\System32\win32kmin.sys`
- `0x140144502`: `\SystemRoot\System32\win32kfull.sys`

## pseudocode

```c
__int64 __fastcall AddApiSetHostLoadRefCount(__int64 a1, const UNICODE_STRING *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v7; // rcx
  ULONG_PTR BugCheckParameter4; // rdi
  ULONG_PTR CurrentProcess; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int ProcessSessionId; // eax
  UNICODE_STRING String2; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING v14; // [rsp+40h] [rbp-30h] BYREF
  UNICODE_STRING v15; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING v16; // [rsp+60h] [rbp-10h] BYREF

  *(_QWORD *)&String2.Length = 4194366;
  *(_QWORD *)&v14.Length = 4718662;
  String2.Buffer = L"\\SystemRoot\\System32\\win32k.sys";
  *(_QWORD *)&v15.Length = 4718662;
  v14.Buffer = L"\\SystemRoot\\System32\\win32kbase.sys";
  *(_QWORD *)&v16.Length = 4587588;
  v15.Buffer = L"\\SystemRoot\\System32\\win32kfull.sys";
  v16.Buffer = L"\\SystemRoot\\System32\\win32kmin.sys";
  v4 = RtlCompareUnicodeString(a2, &String2, 0);
  if ( v4 )
  {
    if ( RtlCompareUnicodeString(a2, &v14, 0) )
    {
      if ( RtlCompareUnicodeString(a2, &v15, 0) )
      {
        if ( RtlCompareUnicodeString(a2, &v16, 0) )
        {
          BugCheckParameter4 = (ULONG_PTR)a2->Buffer;
          CurrentProcess = PsGetCurrentProcess(v7);
          v11 = PsGetCurrentProcess(v10);
          ProcessSessionId = PsGetProcessSessionIdEx(v11);
          KeBugCheckEx(0x164u, 0x37u, ProcessSessionId, CurrentProcess, BugCheckParameter4);
        }
        v4 = 3;
      }
      else
      {
        v4 = 2;
      }
    }
    else
    {
      v4 = 1;
    }
  }
  *(_DWORD *)(a1 + 48) = v4;
  v5 = v4;
  result = gSessionApiSetHostRefCount;
  ++*((_DWORD *)&gSessionApiSetHostRefCount + v5);
  return result;
}

```

## disassembly

```asm
0x1401444b8  mov     [rsp-8+arg_0], rbx
0x1401444bd  mov     [rsp-8+arg_8], rdi
0x1401444c2  push    rbp
0x1401444c3  mov     rbp, rsp
0x1401444c6  sub     rsp, 70h
0x1401444ca  mov     rdi, rdx
0x1401444cd  mov     qword ptr [rbp+String2.Length], 40003Eh
0x1401444d5  lea     rax, aSystemrootSyst_5; "\\SystemRoot\\System32\\win32k.sys"
0x1401444dc  mov     qword ptr [rbp+var_30.Length], 480046h
0x1401444e4  mov     [rbp+String2.Buffer], rax
0x1401444e8  lea     rdx, [rbp+String2]; String2
0x1401444ec  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\win32kbase.sys"
0x1401444f3  mov     qword ptr [rbp+var_20.Length], 480046h
0x1401444fb  mov     [rbp+var_30.Buffer], rax
0x1401444ff  mov     rbx, rcx
0x140144502  lea     rax, aSystemrootSyst_7; "\\SystemRoot\\System32\\win32kfull.sys"
0x140144509  mov     qword ptr [rbp+var_10.Length], 460044h
0x140144511  mov     [rbp+var_20.Buffer], rax
0x140144515  xor     r8d, r8d; CaseInSensitive
0x140144518  lea     rax, aSystemrootSyst_6; "\\SystemRoot\\System32\\win32kmin.sys"
0x14014451f  mov     rcx, rdi; String1
0x140144522  mov     [rbp+var_10.Buffer], rax
0x140144526  call    cs:__imp_RtlCompareUnicodeString
0x14014452d  nop     dword ptr [rax+rax+00h]
0x140144532  test    eax, eax
0x140144534  jnz     short loc_140144558
0x140144536  mov     [rbx+30h], eax
0x140144539  lea     r11, [rsp+70h+var_s0]
0x14014453e  mov     rbx, [r11+10h]
0x140144542  mov     rdi, [r11+18h]
0x140144546  mov     ecx, eax
0x140144548  mov     rax, cs:__imp_gSessionApiSetHostRefCount
0x14014454f  inc     dword ptr [rax+rcx*4]
0x140144552  mov     rsp, r11
0x140144555  pop     rbp
0x140144556  retn
0x140144558  xor     r8d, r8d; CaseInSensitive
0x14014455b  lea     rdx, [rbp+var_30]; String2
0x14014455f  mov     rcx, rdi; String1
0x140144562  call    cs:__imp_RtlCompareUnicodeString
0x140144569  nop     dword ptr [rax+rax+00h]
0x14014456e  test    eax, eax
0x140144570  jz      short loc_140144593
0x140144572  xor     r8d, r8d; CaseInSensitive
0x140144575  lea     rdx, [rbp+var_20]; String2
0x140144579  mov     rcx, rdi; String1
0x14014457c  call    cs:__imp_RtlCompareUnicodeString
0x140144583  nop     dword ptr [rax+rax+00h]
0x140144588  test    eax, eax
0x14014458a  jnz     short loc_14014459A
0x14014458c  mov     eax, 2
0x140144591  jmp     short loc_140144536
0x140144593  mov     eax, 1
0x140144598  jmp     short loc_140144536
0x14014459a  xor     r8d, r8d; CaseInSensitive
0x14014459d  lea     rdx, [rbp+var_10]; String2
0x1401445a1  mov     rcx, rdi; String1
0x1401445a4  call    cs:__imp_RtlCompareUnicodeString
0x1401445ab  nop     dword ptr [rax+rax+00h]
0x1401445b0  test    eax, eax
0x1401445b2  jnz     short loc_1401445BE
0x1401445b4  mov     eax, 3
0x1401445b9  jmp     loc_140144536
0x1401445be  mov     rdi, [rdi+8]
0x1401445c2  call    cs:__imp_PsGetCurrentProcess
0x1401445c9  nop     dword ptr [rax+rax+00h]
0x1401445ce  mov     rbx, rax
0x1401445d1  call    cs:__imp_PsGetCurrentProcess
0x1401445d8  nop     dword ptr [rax+rax+00h]
0x1401445dd  mov     rcx, rax
0x1401445e0  call    cs:__imp_PsGetProcessSessionIdEx
0x1401445e7  nop     dword ptr [rax+rax+00h]
0x1401445ec  mov     r9, rbx; BugCheckParameter3
0x1401445ef  mov     [rsp+70h+BugCheckParameter4], rdi; BugCheckParameter4
0x1401445f4  mov     r8d, eax; BugCheckParameter2
0x1401445f7  mov     edx, 37h ; '7'; BugCheckParameter1
0x1401445fc  mov     ecx, 164h; BugCheckCode
0x140144601  call    cs:__imp_KeBugCheckEx
```
