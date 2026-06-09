# DisallowSharedLanmanNetDrives

- ea: `0x1800290dc`
- end: `0x180029218`
- name: `DisallowSharedLanmanNetDrives`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003f60`

## callees

- `0x1800290dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800291ea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800291ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800291a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800291a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800291fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800291fe`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180029152`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180029152`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18002916f`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800291c5`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18002916f`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800291c5`
- `ntdll!NtClose` at `0x18002918c`
- `ntdll!NtClose` at `0x1800291d1`
- `ntdll!NtClose` at `0x18002918c`
- `ntdll!NtClose` at `0x1800291d1`

## pseudocode

```c
__int64 __fastcall DisallowSharedLanmanNetDrives(__m128i *a1)
{
  __m128i v1; // xmm0
  NTSTATUS v3; // eax
  void *v4; // rcx
  WCHAR *v5; // rax
  unsigned int v6; // edi
  NTSTATUS v7; // ebx
  struct _UNICODE_STRING LinkTarget; // [rsp+20h] [rbp-50h] BYREF
  __m128i v9; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG DataWritten; // [rsp+80h] [rbp+10h] BYREF
  void *SymbolicLinkHandle; // [rsp+88h] [rbp+18h] BYREF

  v1 = *a1;
  SymbolicLinkHandle = 0;
  *(_QWORD *)&LinkTarget.Length = 0;
  DataWritten = 0;
  LinkTarget.Buffer = 0;
  v9 = v1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  v9.m128i_i16[0] = _mm_cvtsi128_si32(v1) - 2;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v9;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) < 0 )
    return 0;
  v3 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -1073741789 )
  {
    v4 = SymbolicLinkHandle;
LABEL_6:
    NtClose(v4);
    return 0;
  }
  LinkTarget.Length = DataWritten;
  LinkTarget.MaximumLength = DataWritten + 2;
  v5 = (WCHAR *)LocalAlloc(0x40u, (unsigned __int16)(DataWritten + 2));
  v4 = SymbolicLinkHandle;
  LinkTarget.Buffer = v5;
  if ( !v5 )
    goto LABEL_6;
  v6 = 0;
  v7 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
  NtClose(SymbolicLinkHandle);
  if ( v7 >= 0 && !(unsigned int)_o__wcsnicmp(LinkTarget.Buffer, L"\\Device\\LanmanRedirector", 24) )
    v6 = 2117;
  LocalFree(LinkTarget.Buffer);
  return v6;
}

```

## disassembly

```asm
0x1800290dc  mov     [rsp-8+arg_10], rbx
0x1800290e1  mov     [rsp-8+arg_18], rdi
0x1800290e6  push    rbp
0x1800290e7  mov     rbp, rsp
0x1800290ea  sub     rsp, 70h
0x1800290ee  movups  xmm0, xmmword ptr [rcx]
0x1800290f1  xor     eax, eax
0x1800290f3  mov     [rbp+SymbolicLinkHandle], 0
0x1800290fb  mov     qword ptr [rbp+LinkTarget.Length], rax
0x1800290ff  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180029103  mov     [rbp+DataWritten], eax
0x180029106  mov     ecx, 0FFFEh
0x18002910b  mov     [rbp+LinkTarget.Buffer], rax
0x18002910f  mov     ebx, 40h ; '@'
0x180029114  movd    eax, xmm0
0x180029118  movups  [rbp+var_40], xmm0
0x18002911c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180029124  xorps   xmm0, xmm0
0x180029127  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002912f  add     ax, cx
0x180029132  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18002913a  mov     word ptr [rbp+var_40], ax
0x18002913e  lea     edx, [rbx-3Fh]; DesiredAccess
0x180029141  lea     rax, [rbp+var_40]
0x180029145  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x180029149  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002914d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180029152  call    cs:__imp_NtOpenSymbolicLinkObject
0x180029158  test    eax, eax
0x18002915a  jns     short loc_180029163
0x18002915c  xor     eax, eax
0x18002915e  jmp     loc_180029206
0x180029163  mov     rcx, [rbp+SymbolicLinkHandle]; SymLinkObjHandle
0x180029167  lea     r8, [rbp+DataWritten]; DataWritten
0x18002916b  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x18002916f  call    cs:__imp_NtQuerySymbolicLinkObject
0x180029175  mov     edx, 80000000h
0x18002917a  lea     ecx, [rax+rdx]
0x18002917d  test    edx, ecx
0x18002917f  jnz     short loc_180029194
0x180029181  cmp     eax, 0C0000023h
0x180029186  jz      short loc_180029194
0x180029188  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x18002918c  call    cs:__imp_NtClose
0x180029192  jmp     short loc_18002915C
0x180029194  mov     eax, [rbp+DataWritten]
0x180029197  mov     ecx, ebx; uFlags
0x180029199  mov     [rbp+LinkTarget.Length], ax
0x18002919d  add     ax, 2
0x1800291a1  movzx   edx, ax; uBytes
0x1800291a4  mov     [rbp+LinkTarget.MaximumLength], dx
0x1800291a8  call    cs:__imp_LocalAlloc
0x1800291ae  mov     rcx, [rbp+SymbolicLinkHandle]; SymLinkObjHandle
0x1800291b2  mov     [rbp+LinkTarget.Buffer], rax
0x1800291b6  test    rax, rax
0x1800291b9  jz      short loc_18002918C
0x1800291bb  lea     r8, [rbp+DataWritten]; DataWritten
0x1800291bf  xor     edi, edi
0x1800291c1  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x1800291c5  call    cs:__imp_NtQuerySymbolicLinkObject
0x1800291cb  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x1800291cf  mov     ebx, eax
0x1800291d1  call    cs:__imp_NtClose
0x1800291d7  test    ebx, ebx
0x1800291d9  js      short loc_1800291FA
0x1800291db  mov     rcx, [rbp+LinkTarget.Buffer]
0x1800291df  lea     r8d, [rdi+18h]
0x1800291e3  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x1800291ea  call    cs:__imp__o__wcsnicmp
0x1800291f0  test    eax, eax
0x1800291f2  mov     ecx, 845h
0x1800291f7  cmovz   edi, ecx
0x1800291fa  mov     rcx, [rbp+LinkTarget.Buffer]; hMem
0x1800291fe  call    cs:__imp_LocalFree
0x180029204  mov     eax, edi
0x180029206  lea     r11, [rsp+70h+var_s0]
0x18002920b  mov     rbx, [r11+20h]
0x18002920f  mov     rdi, [r11+28h]
0x180029213  mov     rsp, r11
0x180029216  pop     rbp
0x180029217  retn
```
