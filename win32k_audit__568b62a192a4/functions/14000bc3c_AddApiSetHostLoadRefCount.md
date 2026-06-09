# AddApiSetHostLoadRefCount

- ea: `0x14000bc3c`
- end: `0x14000bd8f`
- name: `AddApiSetHostLoadRefCount`
- size: `339`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b9ec`

## callees

- `0x14000bc3c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14000bd43`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000bd52`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000bd43`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000bd52`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14000bd61`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14000bd61`
- `ntoskrnl!KeBugCheckEx` at `0x14000bd82`
- `ntoskrnl!KeBugCheckEx` at `0x14000bd82`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bcaa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bcc4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bcde`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bd28`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bcaa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bcc4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bcde`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bd28`

## string_xrefs

- `0x14000bc59`: `\SystemRoot\System32\win32k.sys`
- `0x14000bc70`: `\SystemRoot\System32\win32kbase.sys`
- `0x14000bc9c`: `\SystemRoot\System32\win32kmin.sys`
- `0x14000bc86`: `\SystemRoot\System32\win32kfull.sys`

## pseudocode

```c
__int64 __fastcall AddApiSetHostLoadRefCount(__int64 a1, const UNICODE_STRING *a2)
{
  __int64 result; // rax
  ULONG_PTR BugCheckParameter4; // rdi
  ULONG_PTR CurrentProcess; // rbx
  __int64 v7; // rax
  unsigned int ProcessSessionId; // eax
  UNICODE_STRING String2; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING v10; // [rsp+40h] [rbp-30h] BYREF
  UNICODE_STRING v11; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING v12; // [rsp+60h] [rbp-10h] BYREF

  *(_QWORD *)&String2.Length = 4194366;
  *(_QWORD *)&v10.Length = 4718662;
  String2.Buffer = L"\\SystemRoot\\System32\\win32k.sys";
  *(_QWORD *)&v11.Length = 4718662;
  v10.Buffer = L"\\SystemRoot\\System32\\win32kbase.sys";
  *(_QWORD *)&v12.Length = 4587588;
  v11.Buffer = L"\\SystemRoot\\System32\\win32kfull.sys";
  v12.Buffer = L"\\SystemRoot\\System32\\win32kmin.sys";
  if ( RtlCompareUnicodeString(a2, &String2, 0) )
  {
    if ( RtlCompareUnicodeString(a2, &v10, 0) )
    {
      if ( RtlCompareUnicodeString(a2, &v11, 0) )
      {
        if ( RtlCompareUnicodeString(a2, &v12, 0) )
        {
          BugCheckParameter4 = (ULONG_PTR)a2->Buffer;
          CurrentProcess = PsGetCurrentProcess();
          v7 = PsGetCurrentProcess();
          ProcessSessionId = PsGetProcessSessionIdEx(v7);
          KeBugCheckEx(0x164u, 0x37u, ProcessSessionId, CurrentProcess, BugCheckParameter4);
        }
        result = 3;
      }
      else
      {
        result = 2;
      }
    }
    else
    {
      result = 1;
    }
  }
  else
  {
    result = 0;
  }
  *(_DWORD *)(a1 + 48) = result;
  ++*((_DWORD *)gSessionApiSetHostRefCount + result);
  return result;
}

```

## disassembly

```asm
0x14000bc3c  mov     [rsp-8+arg_0], rbx
0x14000bc41  mov     [rsp-8+arg_8], rdi
0x14000bc46  push    rbp
0x14000bc47  mov     rbp, rsp
0x14000bc4a  sub     rsp, 70h
0x14000bc4e  mov     rdi, rdx
0x14000bc51  mov     qword ptr [rbp+String2.Length], 40003Eh
0x14000bc59  lea     rax, aSystemrootSyst_2; "\\SystemRoot\\System32\\win32k.sys"
0x14000bc60  mov     qword ptr [rbp+var_30.Length], 480046h
0x14000bc68  mov     [rbp+String2.Buffer], rax
0x14000bc6c  lea     rdx, [rbp+String2]; String2
0x14000bc70  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\win32kbase.sys"
0x14000bc77  mov     qword ptr [rbp+var_20.Length], 480046h
0x14000bc7f  mov     [rbp+var_30.Buffer], rax
0x14000bc83  mov     rbx, rcx
0x14000bc86  lea     rax, aSystemrootSyst_4; "\\SystemRoot\\System32\\win32kfull.sys"
0x14000bc8d  mov     qword ptr [rbp+var_10.Length], 460044h
0x14000bc95  mov     [rbp+var_20.Buffer], rax
0x14000bc99  xor     r8d, r8d; CaseInSensitive
0x14000bc9c  lea     rax, aSystemrootSyst_3; "\\SystemRoot\\System32\\win32kmin.sys"
0x14000bca3  mov     rcx, rdi; String1
0x14000bca6  mov     [rbp+var_10.Buffer], rax
0x14000bcaa  call    cs:__imp_RtlCompareUnicodeString
0x14000bcb1  nop     dword ptr [rax+rax+00h]
0x14000bcb6  test    eax, eax
0x14000bcb8  jz      short loc_14000BD1A
0x14000bcba  xor     r8d, r8d; CaseInSensitive
0x14000bcbd  lea     rdx, [rbp+var_30]; String2
0x14000bcc1  mov     rcx, rdi; String1
0x14000bcc4  call    cs:__imp_RtlCompareUnicodeString
0x14000bccb  nop     dword ptr [rax+rax+00h]
0x14000bcd0  test    eax, eax
0x14000bcd2  jz      short loc_14000BD13
0x14000bcd4  xor     r8d, r8d; CaseInSensitive
0x14000bcd7  lea     rdx, [rbp+var_20]; String2
0x14000bcdb  mov     rcx, rdi; String1
0x14000bcde  call    cs:__imp_RtlCompareUnicodeString
0x14000bce5  nop     dword ptr [rax+rax+00h]
0x14000bcea  test    eax, eax
0x14000bcec  jnz     short loc_14000BD1E
0x14000bcee  mov     eax, 2
0x14000bcf3  lea     r11, [rsp+70h+var_s0]
0x14000bcf8  mov     [rbx+30h], eax
0x14000bcfb  mov     rbx, [r11+10h]
0x14000bcff  lea     rcx, gSessionApiSetHostRefCount
0x14000bd06  inc     dword ptr [rcx+rax*4]
0x14000bd09  mov     rdi, [r11+18h]
0x14000bd0d  mov     rsp, r11
0x14000bd10  pop     rbp
0x14000bd11  retn
0x14000bd13  mov     eax, 1
0x14000bd18  jmp     short loc_14000BCF3
0x14000bd1a  xor     eax, eax
0x14000bd1c  jmp     short loc_14000BCF3
0x14000bd1e  xor     r8d, r8d; CaseInSensitive
0x14000bd21  lea     rdx, [rbp+var_10]; String2
0x14000bd25  mov     rcx, rdi; String1
0x14000bd28  call    cs:__imp_RtlCompareUnicodeString
0x14000bd2f  nop     dword ptr [rax+rax+00h]
0x14000bd34  test    eax, eax
0x14000bd36  jnz     short loc_14000BD3F
0x14000bd38  mov     eax, 3
0x14000bd3d  jmp     short loc_14000BCF3
0x14000bd3f  mov     rdi, [rdi+8]
0x14000bd43  call    cs:__imp_PsGetCurrentProcess
0x14000bd4a  nop     dword ptr [rax+rax+00h]
0x14000bd4f  mov     rbx, rax
0x14000bd52  call    cs:__imp_PsGetCurrentProcess
0x14000bd59  nop     dword ptr [rax+rax+00h]
0x14000bd5e  mov     rcx, rax
0x14000bd61  call    cs:__imp_PsGetProcessSessionIdEx
0x14000bd68  nop     dword ptr [rax+rax+00h]
0x14000bd6d  mov     r9, rbx; BugCheckParameter3
0x14000bd70  mov     [rsp+70h+BugCheckParameter4], rdi; BugCheckParameter4
0x14000bd75  mov     r8d, eax; BugCheckParameter2
0x14000bd78  mov     edx, 37h ; '7'; BugCheckParameter1
0x14000bd7d  mov     ecx, 164h; BugCheckCode
0x14000bd82  call    cs:__imp_KeBugCheckEx
```
