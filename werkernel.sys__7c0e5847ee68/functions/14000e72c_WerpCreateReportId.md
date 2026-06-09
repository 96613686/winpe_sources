# WerpCreateReportId

- ea: `0x14000e72c`
- end: `0x14000e835`
- name: `WerpCreateReportId`
- size: `265`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c6f0`

## callees

- `0x1400019a4`
- `0x140002750`
- `0x14000e72c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000e805`
- `ntoskrnl!DbgPrintEx` at `0x14000e805`
- `ntoskrnl!RtlTimeToTimeFields` at `0x14000e796`
- `ntoskrnl!RtlTimeToTimeFields` at `0x14000e796`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x14000e782`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x14000e782`

## pseudocode

```c
__int64 __fastcall WerpCreateReportId(__int64 a1)
{
  _WORD *v2; // rdi
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  int Year; // [rsp+20h] [rbp-60h]
  int Month; // [rsp+28h] [rbp-58h]
  int Day; // [rsp+30h] [rbp-50h]
  int Hour; // [rsp+38h] [rbp-48h]
  int Minute; // [rsp+40h] [rbp-40h]
  union _LARGE_INTEGER SystemTime; // [rsp+50h] [rbp-30h] BYREF
  union _LARGE_INTEGER LocalTime; // [rsp+58h] [rbp-28h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+60h] [rbp-20h] BYREF

  LocalTime.QuadPart = 0;
  TimeFields = 0;
  SystemTime.QuadPart = MEMORY[0xFFFFF78000000014];
  ExSystemTimeToLocalTime(&SystemTime, &LocalTime);
  RtlTimeToTimeFields(&LocalTime, &TimeFields);
  v2 = (_WORD *)(a1 + 56);
  Minute = TimeFields.Minute;
  Hour = TimeFields.Hour;
  Day = TimeFields.Day;
  Month = TimeFields.Month;
  Year = TimeFields.Year;
  v3 = RtlStringCbPrintfW(
         (NTSTRSAFE_PWSTR)(a1 + 56),
         0x50u,
         L"%ws-%04u%02u%02u-%02u%02u.dmp",
         a1 + 24,
         Year,
         Month,
         Day,
         Hour,
         Minute);
  v4 = v3;
  if ( v3 < 0 )
  {
    *v2 = 0;
    DbgPrintEx(5u, 1u, "WERKERNELHOST: RtlStringCbPrintfW failed for wszReportId, status 0x%X.\n", v3);
  }
  return v4;
}

```

## disassembly

```asm
0x14000e72c  mov     [rsp-8+arg_8], rbx
0x14000e731  mov     [rsp-8+arg_10], rdi
0x14000e736  push    rbp
0x14000e737  mov     rbp, rsp
0x14000e73a  sub     rsp, 80h
0x14000e741  mov     rax, cs:__security_cookie
0x14000e748  xor     rax, rsp
0x14000e74b  mov     [rbp+var_10], rax
0x14000e74f  mov     qword ptr [rbp+SystemTime], 0
0x14000e757  lea     rdx, [rbp+LocalTime]; LocalTime
0x14000e75b  xorps   xmm0, xmm0
0x14000e75e  mov     qword ptr [rbp+LocalTime], 0
0x14000e766  movups  xmmword ptr [rbp+TimeFields.Year], xmm0
0x14000e76a  mov     rbx, rcx
0x14000e76d  mov     rax, 0FFFFF78000000014h
0x14000e777  lea     rcx, [rbp+SystemTime]; SystemTime
0x14000e77b  mov     rax, [rax]
0x14000e77e  mov     qword ptr [rbp+SystemTime], rax
0x14000e782  call    cs:__imp_ExSystemTimeToLocalTime
0x14000e789  nop     dword ptr [rax+rax+00h]
0x14000e78e  lea     rdx, [rbp+TimeFields]; TimeFields
0x14000e792  lea     rcx, [rbp+LocalTime]; Time
0x14000e796  call    cs:__imp_RtlTimeToTimeFields
0x14000e79d  nop     dword ptr [rax+rax+00h]
0x14000e7a2  movsx   ecx, [rbp+TimeFields.Hour]
0x14000e7a6  lea     rdi, [rbx+38h]
0x14000e7aa  movsx   edx, [rbp+TimeFields.Day]
0x14000e7ae  lea     r9, [rbx+18h]
0x14000e7b2  movsx   r8d, [rbp+TimeFields.Month]
0x14000e7b7  movsx   eax, [rbp+TimeFields.Minute]
0x14000e7bb  movsx   r10d, [rbp+TimeFields.Year]
0x14000e7c0  mov     [rsp+80h+var_40], eax
0x14000e7c4  mov     [rsp+80h+var_48], ecx
0x14000e7c8  mov     rcx, rdi; pszDest
0x14000e7cb  mov     [rsp+80h+var_50], edx
0x14000e7cf  mov     edx, 50h ; 'P'; cbDest
0x14000e7d4  mov     [rsp+80h+var_58], r8d
0x14000e7d9  lea     r8, aWs04u02u02u02u; "%ws-%04u%02u%02u-%02u%02u.dmp"
0x14000e7e0  mov     [rsp+80h+var_60], r10d
0x14000e7e5  call    RtlStringCbPrintfW
0x14000e7ea  mov     ebx, eax
0x14000e7ec  test    eax, eax
0x14000e7ee  jns     short loc_14000E811
0x14000e7f0  xor     ecx, ecx
0x14000e7f2  lea     r8, aWerkernelhostR_1; "WERKERNELHOST: RtlStringCbPrintfW faile"...
0x14000e7f9  mov     [rdi], cx
0x14000e7fc  mov     r9d, eax
0x14000e7ff  lea     edx, [rcx+1]; Level
0x14000e802  lea     ecx, [rdx+4]; ComponentId
0x14000e805  call    cs:__imp_DbgPrintEx
0x14000e80c  nop     dword ptr [rax+rax+00h]
0x14000e811  mov     eax, ebx
0x14000e813  mov     rcx, [rbp+var_10]
0x14000e817  xor     rcx, rsp; StackCookie
0x14000e81a  call    __security_check_cookie
0x14000e81f  lea     r11, [rsp+80h+var_s0]
0x14000e827  mov     rbx, [r11+18h]
0x14000e82b  mov     rdi, [r11+20h]
0x14000e82f  mov     rsp, r11
0x14000e832  pop     rbp
0x14000e833  retn
```
