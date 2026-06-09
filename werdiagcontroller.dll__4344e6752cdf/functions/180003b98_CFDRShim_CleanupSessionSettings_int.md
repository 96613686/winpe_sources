# CFDRShim::CleanupSessionSettings(int)

- ea: `0x180003b98`
- end: `0x180003d51`
- name: `?CleanupSessionSettings@CFDRShim@@QEAAJH@Z`
- size: `441`
- prototype: `__int64 __fastcall(CFDRShim *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000202c`

## callees

- `0x180001cd4`
- `0x1800039e0`
- `0x180003b58`
- `0x180003b98`
- `0x180003e10`
- `0x18000401c`
- `0x180005158`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180003ce7`
- `ntdll!RtlFreeUnicodeString` at `0x180003ce7`
- `ntdll!DbgPrintEx` at `0x180003bef`
- `ntdll!DbgPrintEx` at `0x180003c3f`
- `ntdll!DbgPrintEx` at `0x180003c8c`
- `ntdll!DbgPrintEx` at `0x180003d02`
- `ntdll!DbgPrintEx` at `0x180003bef`
- `ntdll!DbgPrintEx` at `0x180003c3f`
- `ntdll!DbgPrintEx` at `0x180003c8c`
- `ntdll!DbgPrintEx` at `0x180003d02`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180003cab`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180003cab`
- `ntdll!NtDeleteFile` at `0x180003cdb`
- `ntdll!NtDeleteFile` at `0x180003cdb`

## string_xrefs

- `0x180003be1`: `WERDIAG: Failed reading session settings, cannot delete log file. HRESULT: %08X\n`
- `0x180003d13`: `WERDIAG: Session settings and/or FDR layer were not deleted successfuly. HRESULT: %08X\n`

## pseudocode

```c
__int64 __fastcall CFDRShim::CleanupSessionSettings(CFDRShim *this)
{
  __int64 v1; // rcx
  int updated; // eax
  CFDRShim *v3; // rcx
  int v4; // ebx
  CFDRShim *v5; // rcx
  wchar_t **unique_for; // rax
  wchar_t *v7; // rdi
  int v8; // eax
  NTSTATUS v9; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *v13; // [rsp+90h] [rbp+20h] BYREF
  void *v14; // [rsp+A0h] [rbp+30h] BYREF
  void *v15; // [rsp+A8h] [rbp+38h] BYREF

  v13 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v14 = 0;
  CFDRShim::DeleteFDRLayer(this);
  updated = CFDRShim::ReadAndUpdateSessionSettings(v1, &v14, &v13);
  v4 = updated;
  if ( updated >= 0 )
  {
    CFDRShim::DeleteFDRSessionSettings(v3);
    unique_for = (wchar_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v15, 260);
    v7 = *unique_for;
    *unique_for = 0;
    if ( v15 )
      operator delete[](v15);
    if ( v7 )
    {
      v8 = StringCchPrintfW(v7, 0x104u, L"%s_%d", v13, LODWORD(NtCurrentTeb()->ClientId.UniqueProcess));
      v4 = v8;
      if ( v8 >= 0 )
      {
        NtPathName = 0;
        RtlDosPathNameToNtPathName_U(v7, &NtPathName, 0, 0);
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &NtPathName;
        ObjectAttributes.RootDirectory = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.Attributes = 64;
        v9 = NtDeleteFile(&ObjectAttributes);
        RtlFreeUnicodeString(&NtPathName);
        if ( v9 >= 0
          || (DbgPrintEx(0x96u, 0, "WERDIAG: Failed deleting file. NTSTATUS: %08X\n", v9), v4 = v9 | 0x10000000, v4 >= 0) )
        {
          v4 = 0;
        }
        else
        {
          DbgPrintEx(
            0x96u,
            0,
            "WERDIAG: Session settings and/or FDR layer were not deleted successfuly. HRESULT: %08X\n",
            (unsigned int)v4);
        }
      }
      else
      {
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed appending process ID to log file name. HRESULT: %08X\n", (unsigned int)v8);
      }
      operator delete[](v7);
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Out of resources allocating memory for string buffer\n");
      v4 = -2147024882;
    }
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Failed reading session settings, cannot delete log file. HRESULT: %08X\n", updated);
    CFDRShim::DeleteFDRSessionSettings(v5);
  }
  if ( v14 )
    operator delete[](v14);
  if ( v13 )
    operator delete[](v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003b98  mov     [rsp-18h+arg_0], rcx
0x180003b9d  push    rbp
0x180003b9e  push    rbx
0x180003b9f  push    rdi
0x180003ba0  mov     rbp, rsp
0x180003ba3  sub     rsp, 70h
0x180003ba7  xorps   xmm0, xmm0
0x180003baa  mov     [rbp+arg_0], 0
0x180003bb2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180003bb6  mov     [rbp+arg_10], 0
0x180003bbe  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180003bc2  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180003bc6  call    ?DeleteFDRLayer@CFDRShim@@QEAAJXZ; CFDRShim::DeleteFDRLayer(void)
0x180003bcb  lea     r8, [rbp+arg_0]
0x180003bcf  lea     rdx, [rbp+arg_10]
0x180003bd3  call    ?ReadAndUpdateSessionSettings@CFDRShim@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@0@Z; CFDRShim::ReadAndUpdateSessionSettings(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x180003bd8  mov     ebx, eax
0x180003bda  test    eax, eax
0x180003bdc  jns     short loc_180003BFF
0x180003bde  mov     r9d, eax
0x180003be1  lea     r8, aWerdiagFailedR_4; "WERDIAG: Failed reading session setting"...
0x180003be8  xor     edx, edx; Level
0x180003bea  mov     ecx, 96h; ComponentId
0x180003bef  call    cs:__imp_DbgPrintEx
0x180003bf5  call    ?DeleteFDRSessionSettings@CFDRShim@@AEAAJXZ; CFDRShim::DeleteFDRSessionSettings(void)
0x180003bfa  jmp     loc_180003D29
0x180003bff  call    ?DeleteFDRSessionSettings@CFDRShim@@AEAAJXZ; CFDRShim::DeleteFDRSessionSettings(void)
0x180003c04  mov     ebx, 104h
0x180003c09  lea     rcx, [rbp+arg_18]
0x180003c0d  mov     edx, ebx
0x180003c0f  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180003c14  mov     rdi, [rax]
0x180003c17  mov     qword ptr [rax], 0
0x180003c1e  mov     rcx, [rbp+arg_18]; void *
0x180003c22  test    rcx, rcx
0x180003c25  jz      short loc_180003C2C
0x180003c27  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003c2c  test    rdi, rdi
0x180003c2f  jnz     short loc_180003C4F
0x180003c31  lea     r8, aWerdiagOutOfRe; "WERDIAG: Out of resources allocating me"...
0x180003c38  xor     edx, edx; Level
0x180003c3a  mov     ecx, 96h; ComponentId
0x180003c3f  call    cs:__imp_DbgPrintEx
0x180003c45  mov     ebx, 8007000Eh
0x180003c4a  jmp     loc_180003D29
0x180003c4f  mov     rax, gs:30h
0x180003c58  lea     r8, aSD_0; "%s_%d"
0x180003c5f  mov     r9, [rbp+arg_0]
0x180003c63  mov     rdx, rbx; unsigned __int64
0x180003c66  mov     ecx, [rax+40h]
0x180003c69  mov     [rsp+70h+var_50], ecx
0x180003c6d  mov     rcx, rdi; wchar_t *
0x180003c70  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180003c75  mov     ebx, eax
0x180003c77  test    eax, eax
0x180003c79  jns     short loc_180003C97
0x180003c7b  mov     r9d, eax
0x180003c7e  lea     r8, aWerdiagFailedA; "WERDIAG: Failed appending process ID to"...
0x180003c85  xor     edx, edx; Level
0x180003c87  mov     ecx, 96h; ComponentId
0x180003c8c  call    cs:__imp_DbgPrintEx
0x180003c92  jmp     loc_180003D21
0x180003c97  xorps   xmm0, xmm0
0x180003c9a  lea     rdx, [rbp+NtPathName]; NtPathName
0x180003c9e  xor     r9d, r9d; DirectoryInfo
0x180003ca1  xor     r8d, r8d; NtFileNamePart
0x180003ca4  mov     rcx, rdi; DosPathName
0x180003ca7  movups  xmmword ptr [rbp+NtPathName.Length], xmm0
0x180003cab  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180003cb1  lea     rax, [rbp+NtPathName]
0x180003cb5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180003cbc  xorps   xmm0, xmm0
0x180003cbf  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180003cc3  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x180003cc7  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180003ccf  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180003cd4  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180003cdb  call    cs:__imp_NtDeleteFile
0x180003ce1  lea     rcx, [rbp+NtPathName]; UnicodeString
0x180003ce5  mov     ebx, eax
0x180003ce7  call    cs:__imp_RtlFreeUnicodeString
0x180003ced  test    ebx, ebx
0x180003cef  jns     short loc_180003D1F
0x180003cf1  mov     r9d, ebx
0x180003cf4  lea     r8, aWerdiagFailedD; "WERDIAG: Failed deleting file. NTSTATUS"...
0x180003cfb  xor     edx, edx; Level
0x180003cfd  mov     ecx, 96h; ComponentId
0x180003d02  call    cs:__imp_DbgPrintEx
0x180003d08  or      ebx, 10000000h
0x180003d0e  jge     short loc_180003D1F
0x180003d10  mov     r9d, ebx
0x180003d13  lea     r8, aWerdiagSession; "WERDIAG: Session settings and/or FDR la"...
0x180003d1a  jmp     loc_180003C85
0x180003d1f  xor     ebx, ebx
0x180003d21  mov     rcx, rdi; void *
0x180003d24  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003d29  mov     rcx, [rbp+arg_10]; void *
0x180003d2d  test    rcx, rcx
0x180003d30  jz      short loc_180003D37
0x180003d32  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003d37  cmp     [rbp+arg_0], 0
0x180003d3c  jz      short loc_180003D47
0x180003d3e  mov     rcx, [rbp+arg_0]; void *
0x180003d42  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003d47  mov     eax, ebx
0x180003d49  add     rsp, 70h
0x180003d4d  pop     rdi
0x180003d4e  pop     rbx
0x180003d4f  pop     rbp
0x180003d50  retn
```
