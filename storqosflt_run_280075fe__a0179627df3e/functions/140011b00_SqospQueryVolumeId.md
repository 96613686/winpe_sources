# SqospQueryVolumeId

- ea: `0x140011b00`
- end: `0x140011c54`
- name: `SqospQueryVolumeId`
- size: `340`
- prototype: `__int64 __fastcall(PFLT_VOLUME Volume)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400111bc`
- `0x140011730`

## callees

- `0x140003a80`
- `0x140003ec0`
- `0x14000666c`
- `0x140011b00`

## import_xrefs

- `ntoskrnl!wcschr` at `0x140011bc7`
- `ntoskrnl!wcschr` at `0x140011bc7`
- `ntoskrnl!RtlGUIDFromString` at `0x140011c25`
- `ntoskrnl!RtlGUIDFromString` at `0x140011c25`
- `FLTMGR!FltGetVolumeGuidName` at `0x140011b5e`
- `FLTMGR!FltGetVolumeGuidName` at `0x140011b5e`

## pseudocode

```c
__int64 __fastcall SqospQueryVolumeId(PFLT_VOLUME Volume, char a2, GUID *a3)
{
  int v5; // ebx
  NTSTATUS v6; // eax
  wchar_t *v7; // rax
  WCHAR *v8; // r8
  __int64 v9; // rcx
  __int16 v10; // cx
  NTSTATUS v11; // eax
  struct _UNICODE_STRING VolumeGuidName; // [rsp+20h] [rbp-20h] BYREF
  UNICODE_STRING GuidString; // [rsp+30h] [rbp-10h] BYREF

  GuidString = 0;
  VolumeGuidName = 0;
  if ( byte_14000D2AA && a2 )
  {
LABEL_3:
    v5 = -1073741267;
    goto LABEL_20;
  }
  v5 = SqospAllocateUnicodeString(&VolumeGuidName, 98);
  if ( v5 < 0 )
    goto LABEL_20;
  v6 = FltGetVolumeGuidName(Volume, &VolumeGuidName, 0);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xEu,
        (__int64)WPP_af53c64ad8bd3a498290aca5a9ae070a_Traceguids,
        v6);
    }
    goto LABEL_3;
  }
  VolumeGuidName.Buffer[((unsigned __int64)VolumeGuidName.MaximumLength >> 1) - 1] = 0;
  v7 = wcschr(VolumeGuidName.Buffer, 0x7Bu);
  v8 = v7;
  if ( v7 )
  {
    v9 = 0x7FFF;
    GuidString = 0;
    while ( *v7 )
    {
      ++v7;
      if ( !--v9 )
        goto LABEL_17;
    }
    v10 = 2 * v9;
    GuidString.Buffer = v8;
    GuidString.Length = -2 - v10;
    GuidString.MaximumLength = -v10;
LABEL_17:
    v11 = RtlGUIDFromString(&GuidString, a3);
    if ( v11 < 0 )
      v11 = -1073741489;
    v5 = v11;
  }
  else
  {
    v5 = -1073741489;
  }
LABEL_20:
  SqospFreeUnicodeString((__int64)&VolumeGuidName);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140011b00  push    rbp
0x140011b02  push    rbx
0x140011b03  push    rsi
0x140011b04  push    rdi
0x140011b05  push    r14
0x140011b07  mov     rbp, rsp
0x140011b0a  sub     rsp, 40h
0x140011b0e  xor     r14d, r14d
0x140011b11  xorps   xmm0, xmm0
0x140011b14  cmp     cs:byte_14000D2AA, r14b
0x140011b1b  xorps   xmm1, xmm1
0x140011b1e  mov     rsi, r8
0x140011b21  mov     rdi, rcx
0x140011b24  movups  xmmword ptr [rbp+GuidString.Length], xmm0
0x140011b28  movups  xmmword ptr [rbp+VolumeGuidName.Length], xmm1
0x140011b2c  jz      short loc_140011B3C
0x140011b2e  test    dl, dl
0x140011b30  jz      short loc_140011B3C
0x140011b32  mov     ebx, 0C000022Dh
0x140011b37  jmp     loc_140011C3D
0x140011b3c  mov     edx, 62h ; 'b'
0x140011b41  lea     rcx, [rbp+VolumeGuidName]
0x140011b45  call    SqospAllocateUnicodeString
0x140011b4a  mov     ebx, eax
0x140011b4c  test    eax, eax
0x140011b4e  js      loc_140011C3D
0x140011b54  xor     r8d, r8d; BufferSizeNeeded
0x140011b57  lea     rdx, [rbp+VolumeGuidName]; VolumeGuidName
0x140011b5b  mov     rcx, rdi; Volume
0x140011b5e  call    cs:__imp_FltGetVolumeGuidName
0x140011b65  nop     dword ptr [rax+rax+00h]
0x140011b6a  test    eax, eax
0x140011b6c  jns     short loc_140011BAD
0x140011b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b75  lea     rdx, WPP_GLOBAL_Control
0x140011b7c  cmp     rcx, rdx
0x140011b7f  jz      short loc_140011B32
0x140011b81  mov     edx, [rcx+2Ch]
0x140011b84  test    dl, 10h
0x140011b87  jz      short loc_140011B32
0x140011b89  mov     edx, 2
0x140011b8e  cmp     [rcx+29h], dl
0x140011b91  jb      short loc_140011B32
0x140011b93  mov     rcx, [rcx+18h]
0x140011b97  lea     r8, WPP_af53c64ad8bd3a498290aca5a9ae070a_Traceguids
0x140011b9e  mov     edx, 0Eh
0x140011ba3  mov     r9d, eax
0x140011ba6  call    WPP_SF_d
0x140011bab  jmp     short loc_140011B32
0x140011bad  movzx   edx, [rbp+VolumeGuidName.MaximumLength]
0x140011bb1  mov     rax, [rbp+VolumeGuidName.Buffer]
0x140011bb5  shr     rdx, 1
0x140011bb8  mov     [rax+rdx*2-2], r14w
0x140011bbe  mov     edx, 7Bh ; '{'; Ch
0x140011bc3  mov     rcx, [rbp+VolumeGuidName.Buffer]; Str
0x140011bc7  call    cs:__imp_wcschr
0x140011bce  nop     dword ptr [rax+rax+00h]
0x140011bd3  mov     r8, rax
0x140011bd6  test    rax, rax
0x140011bd9  jnz     short loc_140011BE2
0x140011bdb  mov     ebx, 0C000014Fh
0x140011be0  jmp     short loc_140011C3D
0x140011be2  xorps   xmm0, xmm0
0x140011be5  mov     ecx, 7FFFh
0x140011bea  movups  xmmword ptr [rbp+GuidString.Length], xmm0
0x140011bee  mov     edx, 2
0x140011bf3  cmp     [rax], r14w
0x140011bf7  jz      short loc_140011C04
0x140011bf9  add     rax, rdx
0x140011bfc  sub     rcx, 1
0x140011c00  jnz     short loc_140011BF3
0x140011c02  jmp     short loc_140011C1E
0x140011c04  add     cx, cx
0x140011c07  mov     [rbp+GuidString.Buffer], r8
0x140011c0b  mov     eax, 0FFFEh
0x140011c10  sub     ax, cx
0x140011c13  mov     [rbp+GuidString.Length], ax
0x140011c17  add     ax, dx
0x140011c1a  mov     [rbp+GuidString.MaximumLength], ax
0x140011c1e  mov     rdx, rsi; Guid
0x140011c21  lea     rcx, [rbp+GuidString]; GuidString
0x140011c25  call    cs:__imp_RtlGUIDFromString
0x140011c2c  nop     dword ptr [rax+rax+00h]
0x140011c31  mov     ebx, 0C000014Fh
0x140011c36  test    eax, eax
0x140011c38  cmovs   eax, ebx
0x140011c3b  mov     ebx, eax
0x140011c3d  lea     rcx, [rbp+VolumeGuidName]
0x140011c41  call    SqospFreeUnicodeString
0x140011c46  mov     eax, ebx
0x140011c48  add     rsp, 40h
0x140011c4c  pop     r14
0x140011c4e  pop     rdi
0x140011c4f  pop     rsi
0x140011c50  pop     rbx
0x140011c51  pop     rbp
0x140011c52  retn
```
