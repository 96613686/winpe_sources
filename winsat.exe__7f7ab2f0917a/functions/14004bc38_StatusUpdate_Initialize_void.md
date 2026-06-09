# StatusUpdate::Initialize(void)

- ea: `0x14004bc38`
- end: `0x14004bd17`
- name: `?Initialize@StatusUpdate@@AEAAXXZ`
- size: `223`
- prototype: `void __fastcall(StatusUpdate *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000f5ec`
- `0x14004bbb8`
- `0x14004bd20`
- `0x14004bdb8`

## callees

- `0x140003611`
- `0x14004bc38`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x14004bc77`
- `KERNEL32!OpenEventW` at `0x14004bc90`
- `KERNEL32!OpenEventW` at `0x14004bcab`
- `KERNEL32!OpenEventW` at `0x14004bc77`
- `KERNEL32!OpenEventW` at `0x14004bc90`
- `KERNEL32!OpenEventW` at `0x14004bcab`
- `KERNEL32!MapViewOfFile` at `0x14004bce6`
- `KERNEL32!MapViewOfFile` at `0x14004bce6`
- `KERNEL32!OpenFileMappingW` at `0x14004bc55`
- `KERNEL32!OpenFileMappingW` at `0x14004bc55`

## string_xrefs

- `0x14004bc6d`: `WinSAT.Status.Update`
- `0x14004bc7f`: `WinSAT.Status.Read`

## pseudocode

```c
void __fastcall StatusUpdate::Initialize(StatusUpdate *this)
{
  void *v1; // rax

  if ( !g_Status )
  {
    hFileMappingObject = OpenFileMappingW(6u, 0, L"WinSAT.SharedMemory");
    if ( hFileMappingObject )
    {
      hEvent = OpenEventW(2u, 0, L"WinSAT.Status.Update");
      hHandle = OpenEventW(2u, 0, L"WinSAT.Status.Read");
      qword_1401C6628 = OpenEventW(0x100000u, 0, L"WinSAT.Status.ContinueAssessment");
      if ( hEvent )
      {
        if ( hHandle )
        {
          v1 = MapViewOfFile(hFileMappingObject, 6u, 0, 0, 0x80Cu);
          qword_1401C6610 = (__int64)v1;
          if ( v1 )
          {
            memset_0(v1, 0, 0x80Cu);
            g_Status = 1;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14004bc38  sub     rsp, 38h
0x14004bc3c  cmp     cs:?g_Status@@3VStatusUpdate@@A, 0; StatusUpdate g_Status
0x14004bc43  jnz     loc_14004BD12
0x14004bc49  xor     edx, edx; bInheritHandle
0x14004bc4b  lea     r8, aWinsatSharedme; "WinSAT.SharedMemory"
0x14004bc52  lea     ecx, [rdx+6]; dwDesiredAccess
0x14004bc55  call    cs:__imp_OpenFileMappingW
0x14004bc5b  mov     cs:hFileMappingObject, rax
0x14004bc62  test    rax, rax
0x14004bc65  jz      loc_14004BD12
0x14004bc6b  xor     edx, edx; bInheritHandle
0x14004bc6d  lea     r8, aWinsatStatusUp; "WinSAT.Status.Update"
0x14004bc74  lea     ecx, [rdx+2]; dwDesiredAccess
0x14004bc77  call    cs:__imp_OpenEventW
0x14004bc7d  xor     edx, edx; bInheritHandle
0x14004bc7f  lea     r8, aWinsatStatusRe; "WinSAT.Status.Read"
0x14004bc86  mov     cs:hEvent, rax
0x14004bc8d  lea     ecx, [rdx+2]; dwDesiredAccess
0x14004bc90  call    cs:__imp_OpenEventW
0x14004bc96  lea     r8, aWinsatStatusCo; "WinSAT.Status.ContinueAssessment"
0x14004bc9d  xor     edx, edx; bInheritHandle
0x14004bc9f  mov     ecx, 100000h; dwDesiredAccess
0x14004bca4  mov     cs:hHandle, rax
0x14004bcab  call    cs:__imp_OpenEventW
0x14004bcb1  cmp     cs:hEvent, 0
0x14004bcb9  mov     cs:qword_1401C6628, rax
0x14004bcc0  jz      short loc_14004BD12
0x14004bcc2  cmp     cs:hHandle, 0
0x14004bcca  jz      short loc_14004BD12
0x14004bccc  mov     rcx, cs:hFileMappingObject; hFileMappingObject
0x14004bcd3  xor     r9d, r9d; dwFileOffsetLow
0x14004bcd6  xor     r8d, r8d; dwFileOffsetHigh
0x14004bcd9  mov     [rsp+38h+dwNumberOfBytesToMap], 80Ch; dwNumberOfBytesToMap
0x14004bce2  lea     edx, [r9+6]; dwDesiredAccess
0x14004bce6  call    cs:__imp_MapViewOfFile
0x14004bcec  mov     cs:qword_1401C6610, rax
0x14004bcf3  test    rax, rax
0x14004bcf6  jz      short loc_14004BD12
0x14004bcf8  xor     edx, edx; Val
0x14004bcfa  mov     r8d, 80Ch; Size
0x14004bd00  mov     rcx, rax; void *
0x14004bd03  call    memset_0
0x14004bd08  mov     cs:?g_Status@@3VStatusUpdate@@A, 1; StatusUpdate g_Status
0x14004bd12  add     rsp, 38h
0x14004bd16  retn
```
