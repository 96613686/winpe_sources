# _stub_DCompositionSetBlurredWallpaperSurface

- ea: `0x14003af40`
- end: `0x14003afe7`
- name: `_stub_DCompositionSetBlurredWallpaperSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003af40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003af89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003af89`

## string_xrefs

- `0x14003af6f`: `NtDCompositionSetBlurredWallpaperSurface`

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
0x14003af40  sub     rsp, 48h
0x14003af44  mov     [rsp+48h+var_28], rcx
0x14003af49  mov     [rsp+48h+var_20], rdx
0x14003af4e  mov     [rsp+48h+var_18], r8
0x14003af53  mov     [rsp+48h+var_10], r9
0x14003af58  mov     rcx, 13Ah
0x14003af5f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003af66  nop     dword ptr [rax+rax+00h]
0x14003af6b  test    al, al
0x14003af6d  jz      short loc_14003AFC3
0x14003af6f  lea     rcx, aNtdcomposition_38; "NtDCompositionSetBlurredWallpaperSurfac"...
0x14003af76  mov     rdx, 13Ah
0x14003af7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003af84  nop     dword ptr [rax+rax+00h]
0x14003af89  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003af90  nop     dword ptr [rax+rax+00h]
0x14003af95  test    al, al
0x14003af97  jz      short loc_14003AFC3
0x14003af99  lea     rcx, W32pServiceTableFilter
0x14003afa0  mov     edx, cs:W32pServiceLimitFilter
0x14003afa6  mov     rax, 13Ah
0x14003afad  lea     rcx, [rcx+rdx*4]
0x14003afb1  movsx   eax, byte ptr [rcx+rax]
0x14003afb5  or      eax, eax
0x14003afb7  jle     short loc_14003AFBE
0x14003afb9  mov     eax, 0C000001Ch
0x14003afbe  add     rsp, 48h
0x14003afc2  retn
0x14003afc3  mov     rax, cs:__imp_NtDCompositionSetBlurredWallpaperSurface
0x14003afca  mov     rcx, [rsp+48h+var_28]
0x14003afcf  mov     rdx, [rsp+48h+var_20]
0x14003afd4  mov     r8, [rsp+48h+var_18]
0x14003afd9  mov     r9, [rsp+48h+var_10]
0x14003afde  add     rsp, 48h
0x14003afe2  jmp     rax
```
