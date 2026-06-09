# CFILETIME::SetToUTC(void)

- ea: `0x180008cb4`
- end: `0x180008d00`
- name: `?SetToUTC@CFILETIME@@QEAAXXZ`
- size: `76`
- prototype: `void __fastcall(LPFILETIME lpFileTime)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000297c`
- `0x180003428`
- `0x1800035e4`
- `0x180007f90`
- `0x180009488`
- `0x18000a12c`
- `0x18000a190`
- `0x18000a27c`
- `0x18000be50`
- `0x18000c55c`
- `0x18001011c`
- `0x180010220`

## callees

- `0x180011000`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180008cd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180008cd9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180008ce7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180008ce7`

## pseudocode

```c
void __fastcall CFILETIME::SetToUTC(LPFILETIME lpFileTime)
{
  struct _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-28h] BYREF

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, lpFileTime);
}

```

## disassembly

```asm
0x180008cb4  push    rbx
0x180008cb6  sub     rsp, 40h
0x180008cba  mov     rax, cs:__security_cookie
0x180008cc1  xor     rax, rsp
0x180008cc4  mov     [rsp+48h+var_18], rax
0x180008cc9  mov     rbx, rcx
0x180008ccc  xorps   xmm0, xmm0
0x180008ccf  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x180008cd4  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x180008cd9  call    cs:__imp_GetSystemTime
0x180008cdf  mov     rdx, rbx; lpFileTime
0x180008ce2  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x180008ce7  call    cs:__imp_SystemTimeToFileTime
0x180008ced  mov     rcx, [rsp+48h+var_18]
0x180008cf2  xor     rcx, rsp; StackCookie
0x180008cf5  call    __security_check_cookie
0x180008cfa  add     rsp, 40h
0x180008cfe  pop     rbx
0x180008cff  retn
```
