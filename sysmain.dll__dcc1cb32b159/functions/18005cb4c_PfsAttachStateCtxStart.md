# PfsAttachStateCtxStart

- ea: `0x18005cb4c`
- end: `0x18005cc4d`
- name: `PfsAttachStateCtxStart`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180057284`
- `0x180070e34`
- `0x180073440`
- `0x180083b00`
- `0x18009e35c`
- `0x18009eb40`
- `0x1800a713c`

## callees

- `0x18005cb4c`

## import_xrefs

- `ntdll!NtCreateKey` at `0x18005cc01`
- `ntdll!NtCreateKey` at `0x18005cc01`
- `ntdll!RtlNtStatusToDosError` at `0x18005cc0d`
- `ntdll!RtlNtStatusToDosError` at `0x18005cc0d`
- `ntdll!NtClose` at `0x18005cc30`
- `ntdll!NtClose` at `0x18005cc30`

## string_xrefs

- `0x18005cb63`: `\Registry\Machine\System\CurrentControlSet\Services\RdyBoost\AttachState`

## pseudocode

```c
__int64 __fastcall PfsAttachStateCtxStart(void **a1, int a2)
{
  __int64 v3; // r8
  const wchar_t *v4; // rax
  __int16 v5; // r8
  int v6; // eax
  ULONG v7; // eax
  void *v8; // rcx
  ULONG v9; // ebx
  __int128 v11; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+20h] BYREF

  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  KeyHandle = 0;
  v3 = 0x7FFF;
  v4 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\AttachState";
  v11 = 0;
  while ( *v4 )
  {
    ++v4;
    if ( !--v3 )
      goto LABEL_6;
  }
  v5 = 2 * v3;
  *((_QWORD *)&v11 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\AttachState";
  LOWORD(v11) = -2 - v5;
  WORD1(v11) = -v5;
LABEL_6:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v11;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtCreateKey(&KeyHandle, a2 != 0 ? 131097 : 983103, &ObjectAttributes, 0, 0, 0, 0);
  if ( v6 >= 0 )
  {
    v8 = 0;
    *a1 = KeyHandle;
    v9 = 0;
    KeyHandle = 0;
  }
  else
  {
    v7 = RtlNtStatusToDosError(v6);
    v8 = KeyHandle;
    v9 = v7;
  }
  if ( v8 )
    NtClose(v8);
  return v9;
}

```

## disassembly

```asm
0x18005cb4c  mov     [rsp-8+arg_0], rbx
0x18005cb51  mov     [rsp-8+arg_8], rdi
0x18005cb56  push    rbp
0x18005cb57  mov     rbp, rsp
0x18005cb5a  sub     rsp, 80h
0x18005cb61  xor     edi, edi
0x18005cb63  lea     r9, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18005cb6a  xorps   xmm0, xmm0
0x18005cb6d  mov     dword ptr [rbp+ObjectAttributes+4], edi
0x18005cb70  mov     rbx, rcx
0x18005cb73  mov     dword ptr [rbp+ObjectAttributes+1Ch], edi
0x18005cb76  mov     [rbp+KeyHandle], rdi
0x18005cb7a  mov     r8d, 7FFFh
0x18005cb80  lea     ecx, [rdi+2]
0x18005cb83  mov     rax, r9
0x18005cb86  movups  [rbp+var_40], xmm0
0x18005cb8a  cmp     [rax], di
0x18005cb8d  jz      short loc_18005CB9A
0x18005cb8f  add     rax, rcx
0x18005cb92  sub     r8, 1
0x18005cb96  jnz     short loc_18005CB8A
0x18005cb98  jmp     short loc_18005CBB6
0x18005cb9a  add     r8w, r8w
0x18005cb9e  mov     qword ptr [rbp+var_40+8], r9
0x18005cba2  mov     eax, 0FFFEh
0x18005cba7  sub     ax, r8w
0x18005cbab  mov     word ptr [rbp+var_40], ax
0x18005cbaf  add     ax, cx
0x18005cbb2  mov     word ptr [rbp+var_40+2], ax
0x18005cbb6  neg     edx
0x18005cbb8  mov     [rsp+80h+Disposition], rdi; Disposition
0x18005cbbd  lea     rax, [rbp+var_40]
0x18005cbc1  mov     [rsp+80h+CreateOptions], edi; CreateOptions
0x18005cbc5  sbb     edx, edx
0x18005cbc7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005cbce  and     edx, 0FFF2FFDAh
0x18005cbd4  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x18005cbd8  xorps   xmm0, xmm0
0x18005cbdb  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18005cbe2  add     edx, 0F003Fh; DesiredAccess
0x18005cbe8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18005cbec  xor     r9d, r9d; TitleIndex
0x18005cbef  mov     [rsp+80h+Class], rdi; Class
0x18005cbf4  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005cbf8  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18005cbfc  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005cc01  call    cs:__imp_NtCreateKey
0x18005cc07  test    eax, eax
0x18005cc09  jns     short loc_18005CC1B
0x18005cc0b  mov     ecx, eax; Status
0x18005cc0d  call    cs:__imp_RtlNtStatusToDosError
0x18005cc13  mov     rcx, [rbp+KeyHandle]
0x18005cc17  mov     ebx, eax
0x18005cc19  jmp     short loc_18005CC2B
0x18005cc1b  mov     rax, [rbp+KeyHandle]
0x18005cc1f  mov     rcx, rdi; Handle
0x18005cc22  mov     [rbx], rax
0x18005cc25  mov     ebx, edi
0x18005cc27  mov     [rbp+KeyHandle], rcx
0x18005cc2b  test    rcx, rcx
0x18005cc2e  jz      short loc_18005CC36
0x18005cc30  call    cs:__imp_NtClose
0x18005cc36  lea     r11, [rsp+80h+var_s0]
0x18005cc3e  mov     eax, ebx
0x18005cc40  mov     rbx, [r11+10h]
0x18005cc44  mov     rdi, [r11+18h]
0x18005cc48  mov     rsp, r11
0x18005cc4b  pop     rbp
0x18005cc4c  retn
```
