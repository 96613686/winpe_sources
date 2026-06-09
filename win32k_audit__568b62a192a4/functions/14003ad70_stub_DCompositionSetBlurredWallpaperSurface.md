# _stub_DCompositionSetBlurredWallpaperSurface

- ea: `0x14003ad70`
- end: `0x14003ae17`
- name: `_stub_DCompositionSetBlurredWallpaperSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ad70`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003adb9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003adb9`

## string_xrefs

- `0x14003ad9f`: `NtDCompositionSetBlurredWallpaperSurface`

## pseudocode

```c
__int64 stub_DCompositionSetBlurredWallpaperSurface()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSetBlurredWallpaperSurface();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSetBlurredWallpaperSurface();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ad70  sub     rsp, 48h
0x14003ad74  mov     [rsp+48h+var_28], rcx
0x14003ad79  mov     [rsp+48h+var_20], rdx
0x14003ad7e  mov     [rsp+48h+var_18], r8
0x14003ad83  mov     [rsp+48h+var_10], r9
0x14003ad88  mov     rcx, 13Ah
0x14003ad8f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ad96  nop     dword ptr [rax+rax+00h]
0x14003ad9b  test    al, al
0x14003ad9d  jz      short loc_14003ADF3
0x14003ad9f  lea     rcx, aNtdcomposition_38; "NtDCompositionSetBlurredWallpaperSurfac"...
0x14003ada6  mov     rdx, 13Ah
0x14003adad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003adb4  nop     dword ptr [rax+rax+00h]
0x14003adb9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003adc0  nop     dword ptr [rax+rax+00h]
0x14003adc5  test    al, al
0x14003adc7  jz      short loc_14003ADF3
0x14003adc9  lea     rcx, W32pServiceTableFilter
0x14003add0  mov     edx, cs:W32pServiceLimitFilter
0x14003add6  mov     rax, 13Ah
0x14003addd  lea     rcx, [rcx+rdx*4]
0x14003ade1  movsx   eax, byte ptr [rcx+rax]
0x14003ade5  or      eax, eax
0x14003ade7  jle     short loc_14003ADEE
0x14003ade9  mov     eax, 0C000001Ch
0x14003adee  add     rsp, 48h
0x14003adf2  retn
0x14003adf3  mov     rax, cs:__imp_NtDCompositionSetBlurredWallpaperSurface
0x14003adfa  mov     rcx, [rsp+48h+var_28]
0x14003adff  mov     rdx, [rsp+48h+var_20]
0x14003ae04  mov     r8, [rsp+48h+var_18]
0x14003ae09  mov     r9, [rsp+48h+var_10]
0x14003ae0e  add     rsp, 48h
0x14003ae12  jmp     rax
```
