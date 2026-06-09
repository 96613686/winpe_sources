# AddApiSetHostLoadRefCount

- ea: `0x140142948`
- end: `0x140142a9e`
- name: `AddApiSetHostLoadRefCount`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1401426f8`

## callees

- `0x140142948`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140142a52`
- `ntoskrnl!PsGetCurrentProcess` at `0x140142a61`
- `ntoskrnl!PsGetCurrentProcess` at `0x140142a52`
- `ntoskrnl!PsGetCurrentProcess` at `0x140142a61`
- `ntoskrnl!KeBugCheckEx` at `0x140142a91`
- `ntoskrnl!KeBugCheckEx` at `0x140142a91`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140142a70`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140142a70`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401429b6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401429f2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140142a0c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140142a34`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401429b6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401429f2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140142a0c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140142a34`
- `WIN32K!gSessionApiSetHostRefCount` at `0x1401429d8`

## string_xrefs

- `0x140142965`: `\SystemRoot\System32\win32k.sys`
- `0x14014297c`: `\SystemRoot\System32\win32kbase.sys`
- `0x1401429a8`: `\SystemRoot\System32\win32kmin.sys`
- `0x140142992`: `\SystemRoot\System32\win32kfull.sys`

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
0x140142948  mov     [rsp-8+arg_0], rbx
0x14014294d  mov     [rsp-8+arg_8], rdi
0x140142952  push    rbp
0x140142953  mov     rbp, rsp
0x140142956  sub     rsp, 70h
0x14014295a  mov     rdi, rdx
0x14014295d  mov     qword ptr [rbp+String2.Length], 40003Eh
0x140142965  lea     rax, aSystemrootSyst_5; "\\SystemRoot\\System32\\win32k.sys"
0x14014296c  mov     qword ptr [rbp+var_30.Length], 480046h
0x140142974  mov     [rbp+String2.Buffer], rax
0x140142978  lea     rdx, [rbp+String2]; String2
0x14014297c  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\win32kbase.sys"
0x140142983  mov     qword ptr [rbp+var_20.Length], 480046h
0x14014298b  mov     [rbp+var_30.Buffer], rax
0x14014298f  mov     rbx, rcx
0x140142992  lea     rax, aSystemrootSyst_7; "\\SystemRoot\\System32\\win32kfull.sys"
0x140142999  mov     qword ptr [rbp+var_10.Length], 460044h
0x1401429a1  mov     [rbp+var_20.Buffer], rax
0x1401429a5  xor     r8d, r8d; CaseInSensitive
0x1401429a8  lea     rax, aSystemrootSyst_6; "\\SystemRoot\\System32\\win32kmin.sys"
0x1401429af  mov     rcx, rdi; String1
0x1401429b2  mov     [rbp+var_10.Buffer], rax
0x1401429b6  call    cs:__imp_RtlCompareUnicodeString
0x1401429bd  nop     dword ptr [rax+rax+00h]
0x1401429c2  test    eax, eax
0x1401429c4  jnz     short loc_1401429E8
0x1401429c6  mov     [rbx+30h], eax
0x1401429c9  lea     r11, [rsp+70h+var_s0]
0x1401429ce  mov     rbx, [r11+10h]
0x1401429d2  mov     rdi, [r11+18h]
0x1401429d6  mov     ecx, eax
0x1401429d8  mov     rax, cs:__imp_gSessionApiSetHostRefCount
0x1401429df  inc     dword ptr [rax+rcx*4]
0x1401429e2  mov     rsp, r11
0x1401429e5  pop     rbp
0x1401429e6  retn
0x1401429e8  xor     r8d, r8d; CaseInSensitive
0x1401429eb  lea     rdx, [rbp+var_30]; String2
0x1401429ef  mov     rcx, rdi; String1
0x1401429f2  call    cs:__imp_RtlCompareUnicodeString
0x1401429f9  nop     dword ptr [rax+rax+00h]
0x1401429fe  test    eax, eax
0x140142a00  jz      short loc_140142A23
0x140142a02  xor     r8d, r8d; CaseInSensitive
0x140142a05  lea     rdx, [rbp+var_20]; String2
0x140142a09  mov     rcx, rdi; String1
0x140142a0c  call    cs:__imp_RtlCompareUnicodeString
0x140142a13  nop     dword ptr [rax+rax+00h]
0x140142a18  test    eax, eax
0x140142a1a  jnz     short loc_140142A2A
0x140142a1c  mov     eax, 2
0x140142a21  jmp     short loc_1401429C6
0x140142a23  mov     eax, 1
0x140142a28  jmp     short loc_1401429C6
0x140142a2a  xor     r8d, r8d; CaseInSensitive
0x140142a2d  lea     rdx, [rbp+var_10]; String2
0x140142a31  mov     rcx, rdi; String1
0x140142a34  call    cs:__imp_RtlCompareUnicodeString
0x140142a3b  nop     dword ptr [rax+rax+00h]
0x140142a40  test    eax, eax
0x140142a42  jnz     short loc_140142A4E
0x140142a44  mov     eax, 3
0x140142a49  jmp     loc_1401429C6
0x140142a4e  mov     rdi, [rdi+8]
0x140142a52  call    cs:__imp_PsGetCurrentProcess
0x140142a59  nop     dword ptr [rax+rax+00h]
0x140142a5e  mov     rbx, rax
0x140142a61  call    cs:__imp_PsGetCurrentProcess
0x140142a68  nop     dword ptr [rax+rax+00h]
0x140142a6d  mov     rcx, rax
0x140142a70  call    cs:__imp_PsGetProcessSessionIdEx
0x140142a77  nop     dword ptr [rax+rax+00h]
0x140142a7c  mov     r9, rbx; BugCheckParameter3
0x140142a7f  mov     [rsp+70h+BugCheckParameter4], rdi; BugCheckParameter4
0x140142a84  mov     r8d, eax; BugCheckParameter2
0x140142a87  mov     edx, 37h ; '7'; BugCheckParameter1
0x140142a8c  mov     ecx, 164h; BugCheckCode
0x140142a91  call    cs:__imp_KeBugCheckEx
```
