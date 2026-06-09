# AddApiSetHostLoadRefCount

- ea: `0x140142368`
- end: `0x1401424be`
- name: `AddApiSetHostLoadRefCount`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140142118`

## callees

- `0x140142368`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140142472`
- `ntoskrnl!PsGetCurrentProcess` at `0x140142481`
- `ntoskrnl!PsGetCurrentProcess` at `0x140142472`
- `ntoskrnl!PsGetCurrentProcess` at `0x140142481`
- `ntoskrnl!KeBugCheckEx` at `0x1401424b1`
- `ntoskrnl!KeBugCheckEx` at `0x1401424b1`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140142490`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140142490`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401423d6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140142412`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14014242c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140142454`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401423d6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140142412`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14014242c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140142454`
- `WIN32K!gSessionApiSetHostRefCount` at `0x1401423f8`

## string_xrefs

- `0x140142385`: `\SystemRoot\System32\win32k.sys`
- `0x14014239c`: `\SystemRoot\System32\win32kbase.sys`
- `0x1401423c8`: `\SystemRoot\System32\win32kmin.sys`
- `0x1401423b2`: `\SystemRoot\System32\win32kfull.sys`

## pseudocode

```c
__int64 __fastcall AddApiSetHostLoadRefCount(__int64 a1, const UNICODE_STRING *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  ULONG_PTR BugCheckParameter4; // rdi
  ULONG_PTR CurrentProcess; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rax
  unsigned int ProcessSessionId; // eax
  UNICODE_STRING String2; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING v18; // [rsp+40h] [rbp-30h] BYREF
  UNICODE_STRING v19; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING v20; // [rsp+60h] [rbp-10h] BYREF

  *(_QWORD *)&String2.Length = 4194366;
  *(_QWORD *)&v18.Length = 4718662;
  String2.Buffer = L"\\SystemRoot\\System32\\win32k.sys";
  *(_QWORD *)&v19.Length = 4718662;
  v18.Buffer = L"\\SystemRoot\\System32\\win32kbase.sys";
  *(_QWORD *)&v20.Length = 4587588;
  v19.Buffer = L"\\SystemRoot\\System32\\win32kfull.sys";
  v20.Buffer = L"\\SystemRoot\\System32\\win32kmin.sys";
  v4 = RtlCompareUnicodeString(a2, &String2, 0);
  if ( v4 )
  {
    if ( RtlCompareUnicodeString(a2, &v18, 0) )
    {
      if ( RtlCompareUnicodeString(a2, &v19, 0) )
      {
        if ( RtlCompareUnicodeString(a2, &v20, 0) )
        {
          BugCheckParameter4 = (ULONG_PTR)a2->Buffer;
          CurrentProcess = PsGetCurrentProcess(v8, v7, v9);
          v15 = PsGetCurrentProcess(v13, v12, v14);
          ProcessSessionId = PsGetProcessSessionIdEx(v15);
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
0x140142368  mov     [rsp-8+arg_0], rbx
0x14014236d  mov     [rsp-8+arg_8], rdi
0x140142372  push    rbp
0x140142373  mov     rbp, rsp
0x140142376  sub     rsp, 70h
0x14014237a  mov     rdi, rdx
0x14014237d  mov     qword ptr [rbp+String2.Length], 40003Eh
0x140142385  lea     rax, aSystemrootSyst_5; "\\SystemRoot\\System32\\win32k.sys"
0x14014238c  mov     qword ptr [rbp+var_30.Length], 480046h
0x140142394  mov     [rbp+String2.Buffer], rax
0x140142398  lea     rdx, [rbp+String2]; String2
0x14014239c  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\win32kbase.sys"
0x1401423a3  mov     qword ptr [rbp+var_20.Length], 480046h
0x1401423ab  mov     [rbp+var_30.Buffer], rax
0x1401423af  mov     rbx, rcx
0x1401423b2  lea     rax, aSystemrootSyst_7; "\\SystemRoot\\System32\\win32kfull.sys"
0x1401423b9  mov     qword ptr [rbp+var_10.Length], 460044h
0x1401423c1  mov     [rbp+var_20.Buffer], rax
0x1401423c5  xor     r8d, r8d; CaseInSensitive
0x1401423c8  lea     rax, aSystemrootSyst_6; "\\SystemRoot\\System32\\win32kmin.sys"
0x1401423cf  mov     rcx, rdi; String1
0x1401423d2  mov     [rbp+var_10.Buffer], rax
0x1401423d6  call    cs:__imp_RtlCompareUnicodeString
0x1401423dd  nop     dword ptr [rax+rax+00h]
0x1401423e2  test    eax, eax
0x1401423e4  jnz     short loc_140142408
0x1401423e6  mov     [rbx+30h], eax
0x1401423e9  lea     r11, [rsp+70h+var_s0]
0x1401423ee  mov     rbx, [r11+10h]
0x1401423f2  mov     rdi, [r11+18h]
0x1401423f6  mov     ecx, eax
0x1401423f8  mov     rax, cs:__imp_gSessionApiSetHostRefCount
0x1401423ff  inc     dword ptr [rax+rcx*4]
0x140142402  mov     rsp, r11
0x140142405  pop     rbp
0x140142406  retn
0x140142408  xor     r8d, r8d; CaseInSensitive
0x14014240b  lea     rdx, [rbp+var_30]; String2
0x14014240f  mov     rcx, rdi; String1
0x140142412  call    cs:__imp_RtlCompareUnicodeString
0x140142419  nop     dword ptr [rax+rax+00h]
0x14014241e  test    eax, eax
0x140142420  jz      short loc_140142443
0x140142422  xor     r8d, r8d; CaseInSensitive
0x140142425  lea     rdx, [rbp+var_20]; String2
0x140142429  mov     rcx, rdi; String1
0x14014242c  call    cs:__imp_RtlCompareUnicodeString
0x140142433  nop     dword ptr [rax+rax+00h]
0x140142438  test    eax, eax
0x14014243a  jnz     short loc_14014244A
0x14014243c  mov     eax, 2
0x140142441  jmp     short loc_1401423E6
0x140142443  mov     eax, 1
0x140142448  jmp     short loc_1401423E6
0x14014244a  xor     r8d, r8d; CaseInSensitive
0x14014244d  lea     rdx, [rbp+var_10]; String2
0x140142451  mov     rcx, rdi; String1
0x140142454  call    cs:__imp_RtlCompareUnicodeString
0x14014245b  nop     dword ptr [rax+rax+00h]
0x140142460  test    eax, eax
0x140142462  jnz     short loc_14014246E
0x140142464  mov     eax, 3
0x140142469  jmp     loc_1401423E6
0x14014246e  mov     rdi, [rdi+8]
0x140142472  call    cs:__imp_PsGetCurrentProcess
0x140142479  nop     dword ptr [rax+rax+00h]
0x14014247e  mov     rbx, rax
0x140142481  call    cs:__imp_PsGetCurrentProcess
0x140142488  nop     dword ptr [rax+rax+00h]
0x14014248d  mov     rcx, rax
0x140142490  call    cs:__imp_PsGetProcessSessionIdEx
0x140142497  nop     dword ptr [rax+rax+00h]
0x14014249c  mov     r9, rbx; BugCheckParameter3
0x14014249f  mov     [rsp+70h+BugCheckParameter4], rdi; BugCheckParameter4
0x1401424a4  mov     r8d, eax; BugCheckParameter2
0x1401424a7  mov     edx, 37h ; '7'; BugCheckParameter1
0x1401424ac  mov     ecx, 164h; BugCheckCode
0x1401424b1  call    cs:__imp_KeBugCheckEx
```
