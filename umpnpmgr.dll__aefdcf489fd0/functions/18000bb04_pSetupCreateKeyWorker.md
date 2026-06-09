# pSetupCreateKeyWorker

- ea: `0x18000bb04`
- end: `0x18000bc22`
- name: `pSetupCreateKeyWorker`
- size: `286`
- prototype: `__int64 __fastcall(void *, const WCHAR *, __int64, ULONG, ACCESS_MASK DesiredAccess, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800101e8`

## callees

- `0x18000bb04`
- `0x18000c944`
- `0x1800101d8`

## import_xrefs

- `ntdll!NtCreateKey` at `0x18000bbdb`
- `ntdll!NtCreateKey` at `0x18000bbdb`
- `ntdll!RtlInitUnicodeString` at `0x18000bb77`
- `ntdll!RtlInitUnicodeString` at `0x18000bb77`
- `ntdll!RtlNtStatusToDosError` at `0x18000bbe7`
- `ntdll!RtlNtStatusToDosError` at `0x18000bbe7`

## pseudocode

```c
__int64 __fastcall pSetupCreateKeyWorker(
        void *a1,
        const WCHAR *a2,
        __int64 a3,
        ULONG a4,
        ACCESS_MASK DesiredAccess,
        __int64 a6,
        _QWORD *a7)
{
  void *v7; // rbx
  void *v10; // rsi
  ULONG v11; // edi
  ULONG v12; // eax
  int v13; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+30h] BYREF
  void *v18; // [rsp+C0h] [rbp+40h] BYREF

  KeyHandle = 0;
  v7 = 0;
  v18 = 0;
  v10 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)a1 + 0x80000000 <= 7 )
  {
    v12 = pSetupOpenPredefinedKey(a1, &v18);
    v7 = v18;
    v11 = v12;
    if ( v12 )
      goto LABEL_9;
  }
  else
  {
    v11 = 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  if ( v7 )
    v10 = v7;
  ObjectAttributes.RootDirectory = v10;
  ObjectAttributes.Attributes = (a4 & 8) != 0 ? 448 : 192;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = NtCreateKey(&KeyHandle, DesiredAccess, &ObjectAttributes, 0, 0, a4, 0);
  if ( v13 >= 0 )
    *a7 = (int)KeyHandle;
  else
    v11 = RtlNtStatusToDosError(v13);
LABEL_9:
  if ( v7 )
    pSetupCloseKey((unsigned int)v7);
  return v11;
}

```

## disassembly

```asm
0x18000bb04  mov     [rsp-28h+arg_8], rbx
0x18000bb09  mov     [rsp-28h+arg_10], r8
0x18000bb0e  push    rbp
0x18000bb0f  push    rsi
0x18000bb10  push    rdi
0x18000bb11  push    r14
0x18000bb13  push    r15
0x18000bb15  mov     rbp, rsp
0x18000bb18  sub     rsp, 80h
0x18000bb1f  xor     eax, eax
0x18000bb21  xorps   xmm0, xmm0
0x18000bb24  mov     [rbp+KeyHandle], rax
0x18000bb28  xor     ebx, ebx
0x18000bb2a  mov     eax, 80000000h
0x18000bb2f  mov     [rbp+arg_10], rbx
0x18000bb33  add     rax, rcx
0x18000bb36  mov     r14d, r9d
0x18000bb39  mov     r15, rdx
0x18000bb3c  mov     rsi, rcx
0x18000bb3f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000bb43  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000bb47  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000bb4b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18000bb4f  cmp     rax, 7
0x18000bb53  jbe     short loc_18000BB59
0x18000bb55  xor     edi, edi
0x18000bb57  jmp     short loc_18000BB70
0x18000bb59  lea     rdx, [rbp+arg_10]
0x18000bb5d  call    pSetupOpenPredefinedKey
0x18000bb62  mov     rbx, [rbp+arg_10]
0x18000bb66  mov     edi, eax
0x18000bb68  test    eax, eax
0x18000bb6a  jnz     loc_18000BBFC
0x18000bb70  mov     rdx, r15; SourceString
0x18000bb73  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000bb77  call    cs:__imp_RtlInitUnicodeString
0x18000bb7d  mov     edx, [rbp+DesiredAccess]; DesiredAccess
0x18000bb80  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000bb84  mov     ecx, r14d
0x18000bb87  mov     [rsp+80h+Disposition], 0; Disposition
0x18000bb90  and     ecx, 8
0x18000bb93  mov     [rsp+80h+CreateOptions], r14d; CreateOptions
0x18000bb98  test    rbx, rbx
0x18000bb9b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000bba2  xorps   xmm0, xmm0
0x18000bba5  mov     [rsp+80h+Class], 0; Class
0x18000bbae  cmovnz  rsi, rbx
0x18000bbb2  neg     ecx
0x18000bbb4  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18000bbb8  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18000bbbc  sbb     eax, eax
0x18000bbbe  xor     r9d, r9d; TitleIndex
0x18000bbc1  and     eax, 100h
0x18000bbc6  add     eax, 0C0h
0x18000bbcb  mov     [rbp+ObjectAttributes.Attributes], eax
0x18000bbce  lea     rax, [rbp+DestinationString]
0x18000bbd2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000bbd6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000bbdb  call    cs:__imp_NtCreateKey
0x18000bbe1  test    eax, eax
0x18000bbe3  jns     short loc_18000BBF1
0x18000bbe5  mov     ecx, eax; Status
0x18000bbe7  call    cs:__imp_RtlNtStatusToDosError
0x18000bbed  mov     edi, eax
0x18000bbef  jmp     short loc_18000BBFC
0x18000bbf1  mov     rax, [rbp+arg_30]
0x18000bbf5  movsxd  rcx, dword ptr [rbp+KeyHandle]
0x18000bbf9  mov     [rax], rcx
0x18000bbfc  test    rbx, rbx
0x18000bbff  jz      short loc_18000BC09
0x18000bc01  mov     rcx, rbx
0x18000bc04  call    pSetupCloseKey
0x18000bc09  mov     rbx, [rsp+80h+arg_8]
0x18000bc11  mov     eax, edi
0x18000bc13  add     rsp, 80h
0x18000bc1a  pop     r15
0x18000bc1c  pop     r14
0x18000bc1e  pop     rdi
0x18000bc1f  pop     rsi
0x18000bc20  pop     rbp
0x18000bc21  retn
```
