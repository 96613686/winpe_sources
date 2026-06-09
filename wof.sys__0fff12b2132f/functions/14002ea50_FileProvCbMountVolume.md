# FileProvCbMountVolume

- ea: `0x14002ea50`
- end: `0x14002ebc7`
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
- `0x14002ea50`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14002eabe`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002eabe`
- `ntoskrnl!ObfDereferenceObject` at `0x14002eba1`
- `ntoskrnl!ObfDereferenceObject` at `0x14002eba1`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x14002eb48`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x14002eb48`

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
0x14002ea50  push    rbx
0x14002ea52  push    rsi
0x14002ea53  push    rdi
0x14002ea54  push    r14
0x14002ea56  sub     rsp, 68h
0x14002ea5a  mov     rax, cs:__security_cookie
0x14002ea61  xor     rax, rsp
0x14002ea64  mov     [rsp+88h+var_30], rax
0x14002ea69  mov     eax, cs:dword_14001A4A4
0x14002ea6f  mov     rdi, rcx
0x14002ea72  sub     rdi, rax
0x14002ea75  mov     [rsp+88h+FileObject], 0
0x14002ea7e  xor     eax, eax
0x14002ea80  xorps   xmm0, xmm0
0x14002ea83  mov     [rsp+88h+var_38], rax
0x14002ea88  xor     esi, esi
0x14002ea8a  mov     r14, rcx
0x14002ea8d  movups  [rsp+88h+FsInformation], xmm0
0x14002ea92  lea     r8, [rsp+88h+FileObject]
0x14002ea97  mov     rcx, rdi
0x14002ea9a  call    WofOpenVolumeHandle
0x14002ea9f  mov     ebx, eax
0x14002eaa1  lea     ecx, [rax+7FFFFFF0h]
0x14002eaa7  cmp     ecx, 1
0x14002eaaa  ja      short loc_14002EAD4
0x14002eaac  lea     r8, [rsp+88h+Interval]; Interval
0x14002eab1  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFF0BDC0h
0x14002eaba  xor     edx, edx; Alertable
0x14002eabc  xor     ecx, ecx; WaitMode
0x14002eabe  call    cs:__imp_KeDelayExecutionThread
0x14002eac5  nop     dword ptr [rax+rax+00h]
0x14002eaca  inc     esi
0x14002eacc  cmp     ebx, 80000010h
0x14002ead2  jz      short loc_14002EADC
0x14002ead4  cmp     ebx, 80000011h
0x14002eada  jnz     short loc_14002EAE1
0x14002eadc  cmp     esi, 28h ; '('
0x14002eadf  jb      short loc_14002EA92
0x14002eae1  test    ebx, ebx
0x14002eae3  jns     short loc_14002EB23
0x14002eae5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eaec  mov     eax, [rcx+2Ch]
0x14002eaef  test    al, 8
0x14002eaf1  jz      loc_14002EBAD
0x14002eaf7  cmp     byte ptr [rcx+29h], 2
0x14002eafb  jb      loc_14002EBAD
0x14002eb01  mov     rcx, [rcx+18h]
0x14002eb05  lea     r9, [rdi+40h]
0x14002eb09  mov     edx, 0Bh
0x14002eb0e  mov     [rsp+88h+FsInformationClass], ebx
0x14002eb12  lea     r8, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids
0x14002eb19  call    WPP_SF_Zd
0x14002eb1e  jmp     loc_14002EBAD
0x14002eb23  mov     rdx, [rsp+88h+FileObject]; FileObject
0x14002eb28  lea     r8, [rsp+88h+FsInformation]; FsInformation
0x14002eb2d  mov     rcx, [rdi+78h]; Instance
0x14002eb31  mov     r9d, 18h; Length
0x14002eb37  mov     [rsp+88h+LengthReturned], 0; LengthReturned
0x14002eb40  mov     [rsp+88h+FsInformationClass], 3; FsInformationClass
0x14002eb48  call    cs:__imp_FltQueryVolumeInformationFile
0x14002eb4f  nop     dword ptr [rax+rax+00h]
0x14002eb54  mov     ebx, eax
0x14002eb56  test    eax, eax
0x14002eb58  jns     short loc_14002EB8E
0x14002eb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eb61  mov     edx, [rcx+2Ch]
0x14002eb64  test    dl, 8
0x14002eb67  jz      short loc_14002EB9C
0x14002eb69  cmp     byte ptr [rcx+29h], 2
0x14002eb6d  jb      short loc_14002EB9C
0x14002eb6f  mov     rcx, [rcx+18h]
0x14002eb73  lea     r9, [rdi+40h]
0x14002eb77  mov     edx, 0Ch
0x14002eb7c  mov     [rsp+88h+FsInformationClass], eax
0x14002eb80  lea     r8, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids
0x14002eb87  call    WPP_SF_Zd
0x14002eb8c  jmp     short loc_14002EB9C
0x14002eb8e  mov     eax, dword ptr [rsp+88h+var_38]
0x14002eb92  imul    eax, dword ptr [rsp+88h+var_38+4]
0x14002eb97  xor     ebx, ebx
0x14002eb99  mov     [r14], eax
0x14002eb9c  mov     rcx, [rsp+88h+FileObject]; Object
0x14002eba1  call    cs:__imp_ObfDereferenceObject
0x14002eba8  nop     dword ptr [rax+rax+00h]
0x14002ebad  mov     eax, ebx
0x14002ebaf  mov     rcx, [rsp+88h+var_30]
0x14002ebb4  xor     rcx, rsp; StackCookie
0x14002ebb7  call    __security_check_cookie
0x14002ebbc  add     rsp, 68h
0x14002ebc0  pop     r14
0x14002ebc2  pop     rdi
0x14002ebc3  pop     rsi
0x14002ebc4  pop     rbx
0x14002ebc5  retn
```
