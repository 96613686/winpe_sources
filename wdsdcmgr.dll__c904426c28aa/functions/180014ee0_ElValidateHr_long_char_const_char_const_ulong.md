# ElValidateHr(long,char const *,char const *,ulong)

- ea: `0x180014ee0`
- end: `0x180014f20`
- name: `?ElValidateHr@@YAJJPEBD0K@Z`
- size: `64`
- prototype: `__int64 __fastcall(int, const char *, const char *, unsigned int)`
- caller_count: `90`
- callee_count: `3`
- tags: ``

## callers

- `0x1800013d0`
- `0x1800014c4`
- `0x180001e14`
- `0x1800026ac`
- `0x18000294c`
- `0x180003508`
- `0x1800036dc`
- `0x180003acc`
- `0x1800042f4`
- `0x180005430`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`
- `0x1800063b4`
- `0x180006dfc`
- `0x180007798`
- `0x1800078b0`
- `0x180007960`
- `0x180007f90`
- `0x180009c94`
- `0x18000a3f0`
- `0x18000a870`
- `0x18000b228`
- `0x18000bb58`
- `0x18000bd00`
- `0x18000be10`
- `0x18000bf44`
- `0x18000c03c`
- `0x18000c158`
- `0x18000c2d0`
- `0x18000c774`
- `0x18000e194`
- `0x18000e504`
- `0x18000e6d0`
- `0x18000e750`
- `0x18000e850`
- `0x18000e8f0`
- `0x18000ea90`
- `0x18000eb50`
- `0x18000ec90`
- `0x18000ee00`
- `0x18000ef20`
- `0x18000efb0`
- `0x18000f060`
- `0x18000f160`
- `0x18000f210`
- `0x18000f2c0`
- `0x18000f390`
- `0x18000f470`
- `0x18000f590`

## callees

- `0x180014e1c`
- `0x180014ee0`
- `0x180014f28`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180014ef5`
- `KERNEL32!GetLastError` at `0x180014ef5`
- `KERNEL32!SetLastError` at `0x180014f0d`
- `KERNEL32!SetLastError` at `0x180014f0d`

## pseudocode

```c
__int64 __fastcall ElValidateHr(int a1, const char *a2, const char *a3, unsigned int a4)
{
  DWORD LastError; // edi

  ElValidateHrLite(a1, a2, a3, a4);
  if ( a1 < 0 )
  {
    LastError = GetLastError();
    if ( (g_uErrLibFlags & 1) != 0 )
      ElTraceErrorInfo();
    SetLastError(LastError);
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180014ee0  mov     [rsp+arg_0], rbx
0x180014ee5  push    rdi
0x180014ee6  sub     rsp, 20h
0x180014eea  mov     ebx, ecx
0x180014eec  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x180014ef1  test    ebx, ebx
0x180014ef3  jns     short loc_180014F13
0x180014ef5  call    cs:__imp_GetLastError
0x180014efb  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180014f02  mov     edi, eax
0x180014f04  jz      short loc_180014F0B
0x180014f06  call    ?ElTraceErrorInfo@@YAXXZ; ElTraceErrorInfo(void)
0x180014f0b  mov     ecx, edi; dwErrCode
0x180014f0d  call    cs:__imp_SetLastError
0x180014f13  mov     eax, ebx
0x180014f15  mov     rbx, [rsp+28h+arg_0]
0x180014f1a  add     rsp, 20h
0x180014f1e  pop     rdi
0x180014f1f  retn
```
