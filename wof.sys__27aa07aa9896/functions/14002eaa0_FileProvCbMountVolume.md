# FileProvCbMountVolume

- ea: `0x14002eaa0`
- end: `0x14002ec17`
- name: `FileProvCbMountVolume`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000f148`
- `0x14000fce4`
- `0x140011560`
- `0x14002eaa0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14002eb0e`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002eb0e`
- `ntoskrnl!ObfDereferenceObject` at `0x14002ebf1`
- `ntoskrnl!ObfDereferenceObject` at `0x14002ebf1`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x14002eb98`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x14002eb98`

## pseudocode

```c
__int64 __fastcall FileProvCbMountVolume(_DWORD *a1, __int64 a2)
{
  PFLT_INSTANCE *v2; // rdi
  unsigned int v3; // esi
  int v5; // ebx
  NTSTATUS v6; // eax
  PFILE_OBJECT FileObject; // [rsp+30h] [rbp-58h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+38h] [rbp-50h] BYREF
  __int128 FsInformation; // [rsp+40h] [rbp-48h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]

  v2 = (PFLT_INSTANCE *)((char *)a1 - (unsigned int)dword_14001A4A4);
  FileObject = 0;
  v11 = 0;
  v3 = 0;
  FsInformation = 0;
  do
  {
    v5 = WofOpenVolumeHandle(v2, a2, &FileObject);
    if ( (unsigned int)(v5 + 2147483632) <= 1 )
    {
      Interval.QuadPart = -1000000;
      KeDelayExecutionThread(0, 0, &Interval);
      ++v3;
      if ( v5 == -2147483632 )
        continue;
    }
    if ( v5 != -2147483631 )
      break;
  }
  while ( v3 < 0x28 );
  if ( v5 >= 0 )
  {
    v6 = FltQueryVolumeInformationFile(v2[15], FileObject, &FsInformation, 0x18u, FileFsSizeInformation, 0);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v5 = 0;
      *a1 = HIDWORD(v11) * v11;
    }
    else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Zd(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        (unsigned int)WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids,
        (_DWORD)v2 + 64,
        v6);
    }
    ObfDereferenceObject(FileObject);
  }
  else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Zd(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids,
      (_DWORD)v2 + 64,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002eaa0  push    rbx
0x14002eaa2  push    rsi
0x14002eaa3  push    rdi
0x14002eaa4  push    r14
0x14002eaa6  sub     rsp, 68h
0x14002eaaa  mov     rax, cs:__security_cookie
0x14002eab1  xor     rax, rsp
0x14002eab4  mov     [rsp+88h+var_30], rax
0x14002eab9  mov     eax, cs:dword_14001A4A4
0x14002eabf  mov     rdi, rcx
0x14002eac2  sub     rdi, rax
0x14002eac5  mov     [rsp+88h+FileObject], 0
0x14002eace  xor     eax, eax
0x14002ead0  xorps   xmm0, xmm0
0x14002ead3  mov     [rsp+88h+var_38], rax
0x14002ead8  xor     esi, esi
0x14002eada  mov     r14, rcx
0x14002eadd  movups  [rsp+88h+FsInformation], xmm0
0x14002eae2  lea     r8, [rsp+88h+FileObject]
0x14002eae7  mov     rcx, rdi
0x14002eaea  call    WofOpenVolumeHandle
0x14002eaef  mov     ebx, eax
0x14002eaf1  lea     ecx, [rax+7FFFFFF0h]
0x14002eaf7  cmp     ecx, 1
0x14002eafa  ja      short loc_14002EB24
0x14002eafc  lea     r8, [rsp+88h+Interval]; Interval
0x14002eb01  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFF0BDC0h
0x14002eb0a  xor     edx, edx; Alertable
0x14002eb0c  xor     ecx, ecx; WaitMode
0x14002eb0e  call    cs:__imp_KeDelayExecutionThread
0x14002eb15  nop     dword ptr [rax+rax+00h]
0x14002eb1a  inc     esi
0x14002eb1c  cmp     ebx, 80000010h
0x14002eb22  jz      short loc_14002EB2C
0x14002eb24  cmp     ebx, 80000011h
0x14002eb2a  jnz     short loc_14002EB31
0x14002eb2c  cmp     esi, 28h ; '('
0x14002eb2f  jb      short loc_14002EAE2
0x14002eb31  test    ebx, ebx
0x14002eb33  jns     short loc_14002EB73
0x14002eb35  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eb3c  mov     eax, [rcx+2Ch]
0x14002eb3f  test    al, 8
0x14002eb41  jz      loc_14002EBFD
0x14002eb47  cmp     byte ptr [rcx+29h], 2
0x14002eb4b  jb      loc_14002EBFD
0x14002eb51  mov     rcx, [rcx+18h]
0x14002eb55  lea     r9, [rdi+40h]
0x14002eb59  mov     edx, 0Bh
0x14002eb5e  mov     [rsp+88h+FsInformationClass], ebx
0x14002eb62  lea     r8, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids
0x14002eb69  call    WPP_SF_Zd
0x14002eb6e  jmp     loc_14002EBFD
0x14002eb73  mov     rdx, [rsp+88h+FileObject]; FileObject
0x14002eb78  lea     r8, [rsp+88h+FsInformation]; FsInformation
0x14002eb7d  mov     rcx, [rdi+78h]; Instance
0x14002eb81  mov     r9d, 18h; Length
0x14002eb87  mov     [rsp+88h+LengthReturned], 0; LengthReturned
0x14002eb90  mov     [rsp+88h+FsInformationClass], 3; FsInformationClass
0x14002eb98  call    cs:__imp_FltQueryVolumeInformationFile
0x14002eb9f  nop     dword ptr [rax+rax+00h]
0x14002eba4  mov     ebx, eax
0x14002eba6  test    eax, eax
0x14002eba8  jns     short loc_14002EBDE
0x14002ebaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ebb1  mov     edx, [rcx+2Ch]
0x14002ebb4  test    dl, 8
0x14002ebb7  jz      short loc_14002EBEC
0x14002ebb9  cmp     byte ptr [rcx+29h], 2
0x14002ebbd  jb      short loc_14002EBEC
0x14002ebbf  mov     rcx, [rcx+18h]
0x14002ebc3  lea     r9, [rdi+40h]
0x14002ebc7  mov     edx, 0Ch
0x14002ebcc  mov     [rsp+88h+FsInformationClass], eax
0x14002ebd0  lea     r8, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids
0x14002ebd7  call    WPP_SF_Zd
0x14002ebdc  jmp     short loc_14002EBEC
0x14002ebde  mov     eax, dword ptr [rsp+88h+var_38]
0x14002ebe2  imul    eax, dword ptr [rsp+88h+var_38+4]
0x14002ebe7  xor     ebx, ebx
0x14002ebe9  mov     [r14], eax
0x14002ebec  mov     rcx, [rsp+88h+FileObject]; Object
0x14002ebf1  call    cs:__imp_ObfDereferenceObject
0x14002ebf8  nop     dword ptr [rax+rax+00h]
0x14002ebfd  mov     eax, ebx
0x14002ebff  mov     rcx, [rsp+88h+var_30]
0x14002ec04  xor     rcx, rsp; StackCookie
0x14002ec07  call    __security_check_cookie
0x14002ec0c  add     rsp, 68h
0x14002ec10  pop     r14
0x14002ec12  pop     rdi
0x14002ec13  pop     rsi
0x14002ec14  pop     rbx
0x14002ec15  retn
```
