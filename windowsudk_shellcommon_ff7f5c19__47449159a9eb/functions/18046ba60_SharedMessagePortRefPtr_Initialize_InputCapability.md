# SharedMessagePortRefPtr::Initialize(InputCapability)

- ea: `0x18046ba60`
- end: `0x18046bc0c`
- name: `?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800e4584`

## callees

- `0x18046b9b8`
- `0x18046ba60`
- `0x18046bc74`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046bbf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046bbf0`
- `CoreUIComponents!CoreUIClientCreate` at `0x18046ba88`
- `CoreUIComponents!CoreUIClientCreate` at `0x18046ba88`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18046baf8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18046baf8`

## pseudocode

```c
__int64 __fastcall SharedMessagePortRefPtr::Initialize(_QWORD *a1)
{
  PSECURITY_DESCRIPTOR v2; // r14
  int v3; // eax
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  unsigned int v7; // ebx
  int v8; // r9d
  int v9; // ecx
  unsigned __int64 v10; // r8
  __int64 (__fastcall *v11)(__int64, unsigned __int64, PSECURITY_DESCRIPTOR, _QWORD *); // r11
  const wchar_t *v12; // rax
  const wchar_t *v13; // rdx
  int v14; // ecx
  __int64 v15; // rdi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-18h] BYREF
  const wchar_t *v19; // [rsp+40h] [rbp-10h]
  unsigned __int64 retaddr; // [rsp+78h] [rbp+28h]
  __int64 v21; // [rsp+90h] [rbp+40h] BYREF
  __int64 v22; // [rsp+98h] [rbp+48h] BYREF

  v22 = 0;
  v21 = 0;
  v2 = 0;
  v3 = CoreUIClientCreate(&v22);
  v7 = v3;
  if ( v3 < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_24;
    v8 = 115;
    goto LABEL_4;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v21);
  v7 = v3;
  if ( v3 >= 0 )
  {
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;;;S-1-15-3-1024-1502825166-1963708345-2616377461-2562897074-419202837"
             "2-3968301570-1997628692-1435953622)",
            1u,
            &SecurityDescriptor,
            0) )
      FailFastWithHR(v9, retaddr, v10);
    v2 = SecurityDescriptor;
    SecurityDescriptor = 0;
    v11 = *(__int64 (__fastcall **)(__int64, unsigned __int64, PSECURITY_DESCRIPTOR, _QWORD *))(*(_QWORD *)v21 + 24LL);
    v12 = L"Input\\Service.AlpcPort\\Server";
    if ( L"Input\\Service.AlpcPort\\Server" )
    {
      v13 = L"Input\\Service.AlpcPort\\Server";
      v19 = L"Input\\Service.AlpcPort\\Server";
      v14 = 0;
      while ( *v12 )
      {
        ++v12;
        ++v14;
      }
      v18 = v14 | 0x80000000;
    }
    else
    {
      v13 = 0;
      v19 = 0;
    }
    v3 = v11(v21, (unsigned __int64)&v18 & -(__int64)(v13 != 0), v2, a1 + 1);
    v7 = v3;
    if ( v3 >= 0 )
    {
      v15 = v21;
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
      if ( *a1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      *a1 = v15;
    }
    else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      v8 = 126;
      goto LABEL_4;
    }
  }
  else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
  {
    v8 = 118;
LABEL_4:
    McTemplateU0sqq_EventWriteTransfer(v5, v4, v6, v8, v3);
  }
LABEL_24:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  LocalFree(v2);
  return v7;
}

```

## disassembly

```asm
0x18046ba60  mov     [rsp-28h+arg_0], rbx
0x18046ba65  push    rbp
0x18046ba66  push    rsi
0x18046ba67  push    rdi
0x18046ba68  push    r14
0x18046ba6a  push    r15
0x18046ba6c  mov     rbp, rsp
0x18046ba6f  sub     rsp, 50h
0x18046ba73  xor     r15d, r15d
0x18046ba76  mov     rsi, rcx
0x18046ba79  lea     rcx, [rbp+arg_18]
0x18046ba7d  mov     [rbp+arg_18], r15
0x18046ba81  mov     [rbp+arg_10], r15
0x18046ba85  mov     r14d, r15d
0x18046ba88  call    cs:__imp_CoreUIClientCreate
0x18046ba8e  mov     ebx, eax
0x18046ba90  test    eax, eax
0x18046ba92  jns     short loc_18046BAB3
0x18046ba94  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18046ba9b  jz      loc_18046BBBB
0x18046baa1  lea     r9d, [r15+73h]
0x18046baa5  mov     [rsp+50h+var_30], eax
0x18046baa9  call    McTemplateU0sqq_EventWriteTransfer
0x18046baae  jmp     loc_18046BBBB
0x18046bab3  mov     rcx, [rbp+arg_18]
0x18046bab7  lea     rdx, [rbp+arg_10]
0x18046babb  mov     rax, [rcx]
0x18046babe  mov     rax, [rax+30h]
0x18046bac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18046bac7  mov     ebx, eax
0x18046bac9  test    eax, eax
0x18046bacb  jns     short loc_18046BAE2
0x18046bacd  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18046bad4  jz      loc_18046BBBB
0x18046bada  mov     r9d, 76h ; 'v'
0x18046bae0  jmp     short loc_18046BAA5
0x18046bae2  xor     r9d, r9d; SecurityDescriptorSize
0x18046bae5  mov     [rbp+SecurityDescriptor], r15
0x18046bae9  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18046baed  lea     rcx, aDA0x01WdA0x01A; "D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;"...
0x18046baf4  lea     edx, [r9+1]; StringSDRevision
0x18046baf8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18046bafe  test    eax, eax
0x18046bb00  jnz     short loc_18046BB0B
0x18046bb02  mov     rdx, [rbp+28h]; unsigned __int64
0x18046bb06  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x18046bb0b  mov     r10, [rbp+arg_10]
0x18046bb0f  mov     r14, [rbp+SecurityDescriptor]
0x18046bb13  mov     [rbp+SecurityDescriptor], r15
0x18046bb17  mov     rax, [r10]
0x18046bb1a  mov     r11, [rax+18h]
0x18046bb1e  mov     rax, cs:off_1804EB088; "Input\\Service.AlpcPort\\Server"
0x18046bb25  test    rax, rax
0x18046bb28  jz      short loc_18046BB4C
0x18046bb2a  mov     rdx, rax
0x18046bb2d  mov     [rbp+var_10], rax
0x18046bb31  mov     rcx, r15
0x18046bb34  jmp     short loc_18046BB3D
0x18046bb36  lea     rax, [rax+2]
0x18046bb3a  inc     rcx
0x18046bb3d  cmp     [rax], r15w
0x18046bb41  jnz     short loc_18046BB36
0x18046bb43  bts     ecx, 1Fh
0x18046bb47  mov     [rbp+var_18], ecx
0x18046bb4a  jmp     short loc_18046BB53
0x18046bb4c  mov     rdx, r15
0x18046bb4f  mov     [rbp+var_10], rdx
0x18046bb53  neg     rdx
0x18046bb56  lea     rax, [rbp+var_18]
0x18046bb5a  lea     r9, [rsi+8]
0x18046bb5e  mov     r8, r14
0x18046bb61  sbb     rdx, rdx
0x18046bb64  mov     rcx, r10
0x18046bb67  and     rdx, rax
0x18046bb6a  mov     rax, r11
0x18046bb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18046bb72  mov     ebx, eax
0x18046bb74  test    eax, eax
0x18046bb76  jns     short loc_18046BB8C
0x18046bb78  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18046bb7f  jz      short loc_18046BBBB
0x18046bb81  mov     r9d, 7Eh ; '~'
0x18046bb87  jmp     loc_18046BAA5
0x18046bb8c  mov     rdi, [rbp+arg_10]
0x18046bb90  test    rdi, rdi
0x18046bb93  jz      short loc_18046BBA4
0x18046bb95  mov     rax, [rdi]
0x18046bb98  mov     rcx, rdi
0x18046bb9b  mov     rax, [rax+8]
0x18046bb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18046bba4  mov     rcx, [rsi]
0x18046bba7  test    rcx, rcx
0x18046bbaa  jz      short loc_18046BBB8
0x18046bbac  mov     rax, [rcx]
0x18046bbaf  mov     rax, [rax+10h]
0x18046bbb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18046bbb8  mov     [rsi], rdi
0x18046bbbb  mov     rcx, [rbp+arg_18]
0x18046bbbf  test    rcx, rcx
0x18046bbc2  jz      short loc_18046BBD4
0x18046bbc4  mov     rax, [rcx]
0x18046bbc7  mov     rax, [rax+10h]
0x18046bbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18046bbd0  mov     [rbp+arg_18], r15
0x18046bbd4  mov     rcx, [rbp+arg_10]
0x18046bbd8  test    rcx, rcx
0x18046bbdb  jz      short loc_18046BBED
0x18046bbdd  mov     rax, [rcx]
0x18046bbe0  mov     rax, [rax+10h]
0x18046bbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18046bbe9  mov     [rbp+arg_10], r15
0x18046bbed  mov     rcx, r14; hMem
0x18046bbf0  call    cs:__imp_LocalFree
0x18046bbf6  mov     eax, ebx
0x18046bbf8  mov     rbx, [rsp+50h+arg_0]
0x18046bc00  add     rsp, 50h
0x18046bc04  pop     r15
0x18046bc06  pop     r14
0x18046bc08  pop     rdi
0x18046bc09  pop     rsi
0x18046bc0a  pop     rbp
0x18046bc0b  retn
```
