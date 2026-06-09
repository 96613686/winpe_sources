# SmpRunSecureKernelTrustlets

- ea: `0x140016190`
- end: `0x1400165f3`
- name: `SmpRunSecureKernelTrustlets`
- size: `1123`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x1400010ec`
- `0x140003450`
- `0x140012d10`
- `0x140012de0`
- `0x140016190`
- `0x14001c14c`
- `0x14001c7cc`
- `0x14001c8a4`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001620e`
- `ntdll!RtlInitUnicodeString` at `0x140016220`
- `ntdll!RtlInitUnicodeString` at `0x14001620e`
- `ntdll!RtlInitUnicodeString` at `0x140016220`
- `ntdll!NtClose` at `0x14001634c`
- `ntdll!NtClose` at `0x140016586`
- `ntdll!NtClose` at `0x1400165c1`
- `ntdll!NtClose` at `0x14001634c`
- `ntdll!NtClose` at `0x140016586`
- `ntdll!NtClose` at `0x1400165c1`
- `ntdll!RtlAllocateHeap` at `0x1400162d3`
- `ntdll!RtlAllocateHeap` at `0x140016466`
- `ntdll!RtlAllocateHeap` at `0x1400162d3`
- `ntdll!RtlAllocateHeap` at `0x140016466`
- `ntdll!RtlFreeHeap` at `0x1400162b3`
- `ntdll!RtlFreeHeap` at `0x14001651f`
- `ntdll!RtlFreeHeap` at `0x1400165af`
- `ntdll!RtlFreeHeap` at `0x1400162b3`
- `ntdll!RtlFreeHeap` at `0x14001651f`
- `ntdll!RtlFreeHeap` at `0x1400165af`
- `ntdll!NtQueryValueKey` at `0x1400163b8`
- `ntdll!NtQueryValueKey` at `0x1400163b8`

## string_xrefs

- `0x14001637d`: `Failed to open interface key.`
- `0x1400163cc`: `SecureKernelTrustlet registry key not found`
- `0x140016546`: `Registry Buffer too small`
- `0x1400163f9`: `Failed to query SecureKernelTrustlet registry value.`
- `0x140016417`: `SecureKernelTrustlet registry value is the wrong type.`
- `0x14001652d`: `Provided trustlet path is too long.`
- `0x14001647c`: `Failed to allocate memory for trustlet path buffer.`
- `0x1400164b2`: `Failed to add prefix to trustlet path.`
- `0x1400164e0`: `Failed to append registry data to trustlet path.`

## pseudocode

```c
__int64 __fastcall SmpRunSecureKernelTrustlets(_BYTE *a1)
{
  HANDLE v2; // r15
  int v3; // eax
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  unsigned int v7; // ebx
  wchar_t *Heap; // rdi
  unsigned int v9; // r14d
  int DeviceInterfaceList; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  wchar_t *v13; // r12
  int v14; // eax
  __int64 v15; // r9
  const wchar_t *v16; // r8
  __int64 v17; // rdx
  USHORT v18; // r14
  NTSTATUS v19; // eax
  const wchar_t *v20; // r8
  __int64 v21; // rdx
  int v22; // r8d
  __int64 v23; // rax
  __int64 ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v26; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+74h] [rbp-8Ch]
  unsigned int v32; // [rsp+78h] [rbp-88h]
  wchar_t pszSrc[514]; // [rsp+7Ch] [rbp-84h] BYREF
  _BYTE BaseAddress[1024]; // [rsp+480h] [rbp+380h] BYREF

  DestinationString = 0;
  v26 = 0;
  SourceString = 0;
  memset_0(BaseAddress, 0, sizeof(BaseAddress));
  ResultLength = 0;
  v2 = 0;
  KeyHandle = 0;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, L"SecureKernelTrustlet");
  RtlInitUnicodeString(&SourceString, L"async secure ");
  v3 = NtPnpInitializeLibrary();
  v7 = v3;
  if ( v3 < 0 )
  {
    SmpLogFailureString("SmpRunSecureKernelTrustlets", 2039, L"Failed to initialize NtPnpApi.", (unsigned int)v3);
    return v7;
  }
  Heap = (wchar_t *)BaseAddress;
  v9 = 512;
  while ( 1 )
  {
    DeviceInterfaceList = NtPnpGetDeviceInterfaceList(v5, v4, v6, v9, Heap, (__int64)&ResultLength);
    v7 = DeviceInterfaceList;
    if ( DeviceInterfaceList != -1073741789 )
      break;
    if ( (unsigned int)ResultLength <= v9 )
    {
      v7 = -1073741595;
      SmpLogFailureString(
        "SmpRunSecureKernelTrustlets",
        2070,
        L"Retrieving the list of interfaces returned that the buffer is too small but the required size is not larger.",
        3221225701LL);
      goto LABEL_13;
    }
    if ( Heap && Heap != (wchar_t *)BaseAddress )
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
    v9 = ResultLength;
    Heap = (wchar_t *)RtlAllocateHeap(
                        *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                        0,
                        2LL * (unsigned int)ResultLength);
    if ( !Heap )
    {
      v7 = -1073741670;
LABEL_13:
      SmpLogFailureString("SmpRunSecureKernelTrustlets", 2094, L"Failed to get list of interfaces.", v7);
      goto LABEL_49;
    }
  }
  if ( DeviceInterfaceList < 0 )
    goto LABEL_13;
  v13 = Heap;
  if ( !*Heap )
    goto LABEL_49;
  do
  {
    if ( v2 )
    {
      NtClose(v2);
      KeyHandle = 0;
    }
    v14 = NtPnpOpenDeviceInterfaceKey(v13, v11, v12, &KeyHandle);
    v2 = KeyHandle;
    v7 = v14;
    if ( v14 != -1073741772 )
    {
      if ( v14 < 0 )
      {
        v15 = (unsigned int)v14;
        v16 = L"Failed to open interface key.";
        v17 = 2120;
        goto LABEL_43;
      }
      HIDWORD(ResultLength) = 0;
      v7 = NtQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x410u,
             (PULONG)&ResultLength + 1);
      if ( v7 == -1073741772 )
      {
        v15 = 3221225524LL;
        v16 = L"SecureKernelTrustlet registry key not found";
        v17 = 2135;
        goto LABEL_43;
      }
      if ( v7 == -2147483643 || v7 == -1073741789 )
      {
        v16 = L"Registry Buffer too small";
        v17 = 2142;
LABEL_42:
        v15 = v7;
LABEL_43:
        SmpLogFailureString("SmpRunSecureKernelTrustlets", v17, v16, v15);
        goto LABEL_44;
      }
      if ( (v7 & 0x80000000) != 0 )
      {
        v16 = L"Failed to query SecureKernelTrustlet registry value.";
        v17 = 2148;
        goto LABEL_42;
      }
      if ( v31 != 1 )
      {
        v15 = 3221225508LL;
        v16 = L"SecureKernelTrustlet registry value is the wrong type.";
        v17 = 2156;
        goto LABEL_43;
      }
      v18 = SourceString.Length + v32;
      if ( (unsigned __int16)(SourceString.Length + v32) < SourceString.Length || v18 < v32 )
      {
        v15 = 3221225485LL;
        v16 = L"Provided trustlet path is too long.";
        v17 = 2164;
        goto LABEL_43;
      }
      *a1 = 1;
      v26.Buffer = (PWSTR)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v18);
      if ( !v26.Buffer )
      {
        v15 = 3221225626LL;
        v16 = L"Failed to allocate memory for trustlet path buffer.";
        v17 = 2178;
        goto LABEL_43;
      }
      v26.MaximumLength = v18;
      v26.Length = 0;
      v19 = RtlUnicodeStringCat(&v26, &SourceString);
      v7 = v19;
      if ( v19 >= 0 )
      {
        v19 = RtlUnicodeStringCatString(&v26, pszSrc);
        v7 = v19;
        if ( v19 >= 0 )
        {
          v7 = SmpExecuteCommand((unsigned int)&v26, 0, v22, 0, 0);
LABEL_38:
          if ( v26.Buffer )
            RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v26.Buffer);
          goto LABEL_44;
        }
        v20 = L"Failed to append registry data to trustlet path.";
        v21 = 2197;
      }
      else
      {
        v20 = L"Failed to add prefix to trustlet path.";
        v21 = 2189;
      }
      SmpLogFailureString("SmpRunSecureKernelTrustlets", v21, v20, (unsigned int)v19);
      goto LABEL_38;
    }
LABEL_44:
    v23 = -1;
    do
      ++v23;
    while ( v13[v23] );
    v13 += v23 + 1;
  }
  while ( *v13 );
  if ( v2 )
    NtClose(v2);
LABEL_49:
  if ( Heap && Heap != (wchar_t *)BaseAddress )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
  if ( NtPnpDeviceApiDriverHandle )
  {
    NtClose(NtPnpDeviceApiDriverHandle);
    NtPnpDeviceApiDriverHandle = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x140016190  push    rbp
0x140016192  push    rbx
0x140016193  push    rsi
0x140016194  push    rdi
0x140016195  push    r12
0x140016197  push    r13
0x140016199  push    r14
0x14001619b  push    r15
0x14001619d  lea     rbp, [rsp-798h]
0x1400161a5  sub     rsp, 898h
0x1400161ac  mov     rax, cs:__security_cookie
0x1400161b3  xor     rax, rsp
0x1400161b6  mov     [rbp+7D0h+var_50], rax
0x1400161bd  xorps   xmm0, xmm0
0x1400161c0  mov     r13, rcx
0x1400161c3  xorps   xmm1, xmm1
0x1400161c6  lea     rcx, [rbp+7D0h+BaseAddress]; void *
0x1400161cd  xor     edx, edx; Val
0x1400161cf  mov     r8d, 400h; Size
0x1400161d5  movups  xmmword ptr [rsp+8D0h+DestinationString.Length], xmm0
0x1400161da  movups  xmmword ptr [rsp+8D0h+var_898.Length], xmm1
0x1400161df  movups  xmmword ptr [rsp+8D0h+SourceString.Length], xmm0
0x1400161e4  call    memset_0
0x1400161e9  xor     r12d, r12d
0x1400161ec  lea     rdx, aSecurekerneltr; "SecureKernelTrustlet"
0x1400161f3  lea     rcx, [rsp+8D0h+DestinationString]; DestinationString
0x1400161f8  mov     dword ptr [rsp+8D0h+var_8A0], r12d
0x1400161fd  mov     r15d, r12d
0x140016200  mov     [rsp+8D0h+KeyHandle], r12
0x140016205  mov     dword ptr [rsp+8D0h+var_8A0+4], r12d
0x14001620a  mov     [r13+0], r12b
0x14001620e  call    cs:__imp_RtlInitUnicodeString
0x140016214  lea     rdx, aAsyncSecure; "async secure "
0x14001621b  lea     rcx, [rsp+8D0h+SourceString]; DestinationString
0x140016220  call    cs:__imp_RtlInitUnicodeString
0x140016226  call    NtPnpInitializeLibrary
0x14001622b  mov     ebx, eax
0x14001622d  test    eax, eax
0x14001622f  jns     short loc_140016251
0x140016231  mov     r9d, eax
0x140016234  lea     r8, aFailedToInitia; "Failed to initialize NtPnpApi."
0x14001623b  mov     edx, 7F7h
0x140016240  lea     rcx, aSmprunsecureke; "SmpRunSecureKernelTrustlets"
0x140016247  call    SmpLogFailureString
0x14001624c  jmp     loc_1400165CE
0x140016251  lea     rdi, [rbp+7D0h+BaseAddress]
0x140016258  mov     r14d, 200h
0x14001625e  lea     rax, [rsp+8D0h+var_8A0]
0x140016263  mov     r9d, r14d; int
0x140016266  mov     [rsp+8D0h+ResultLength], rax; __int64
0x14001626b  mov     qword ptr [rsp+8D0h+Length], rdi; pszDest
0x140016270  call    NtPnpGetDeviceInterfaceList
0x140016275  lea     rsi, aSmprunsecureke; "SmpRunSecureKernelTrustlets"
0x14001627c  mov     ebx, eax
0x14001627e  cmp     eax, 0C0000023h
0x140016283  jnz     loc_14001630D
0x140016289  cmp     dword ptr [rsp+8D0h+var_8A0], r14d
0x14001628e  jbe     short loc_1400162EC
0x140016290  test    rdi, rdi
0x140016293  jz      short loc_1400162B9
0x140016295  lea     rax, [rbp+7D0h+BaseAddress]
0x14001629c  cmp     rdi, rax
0x14001629f  jz      short loc_1400162B9
0x1400162a1  mov     rcx, gs:60h
0x1400162aa  mov     r8, rdi; BaseAddress
0x1400162ad  xor     edx, edx; Flags
0x1400162af  mov     rcx, [rcx+30h]; HeapHandle
0x1400162b3  call    cs:__imp_RtlFreeHeap
0x1400162b9  mov     rcx, gs:60h
0x1400162c2  xor     edx, edx; Flags
0x1400162c4  mov     r14d, dword ptr [rsp+8D0h+var_8A0]
0x1400162c9  mov     r8d, r14d
0x1400162cc  add     r8, r8; Size
0x1400162cf  mov     rcx, [rcx+30h]; HeapHandle
0x1400162d3  call    cs:__imp_RtlAllocateHeap
0x1400162d9  mov     rdi, rax
0x1400162dc  test    rax, rax
0x1400162df  jnz     loc_14001625E
0x1400162e5  mov     ebx, 0C000009Ah
0x1400162ea  jmp     short loc_140016308
0x1400162ec  mov     ebx, 0C00000E5h
0x1400162f1  lea     r8, aRetrievingTheL; "Retrieving the list of interfaces retur"...
0x1400162f8  mov     r9d, ebx
0x1400162fb  mov     edx, 816h
0x140016300  mov     rcx, rsi
0x140016303  call    SmpLogFailureString
0x140016308  xor     r14d, r14d
0x14001630b  jmp     short loc_140016314
0x14001630d  xor     r14d, r14d
0x140016310  test    eax, eax
0x140016312  jns     short loc_140016330
0x140016314  mov     r9d, ebx
0x140016317  lea     r8, aFailedToGetLis; "Failed to get list of interfaces."
0x14001631e  mov     edx, 82Eh
0x140016323  mov     rcx, rsi
0x140016326  call    SmpLogFailureString
0x14001632b  jmp     loc_14001658C
0x140016330  mov     r12, rdi
0x140016333  cmp     [rdi], r14w
0x140016337  jz      loc_14001658C
0x14001633d  lea     rsi, aSmprunsecureke; "SmpRunSecureKernelTrustlets"
0x140016344  test    r15, r15
0x140016347  jz      short loc_140016357
0x140016349  mov     rcx, r15; Handle
0x14001634c  call    cs:__imp_NtClose
0x140016352  mov     [rsp+8D0h+KeyHandle], r14
0x140016357  lea     r9, [rsp+8D0h+KeyHandle]
0x14001635c  mov     rcx, r12
0x14001635f  call    NtPnpOpenDeviceInterfaceKey
0x140016364  mov     r15, [rsp+8D0h+KeyHandle]
0x140016369  mov     ebx, eax
0x14001636b  cmp     eax, 0C0000034h
0x140016370  jz      loc_14001655D
0x140016376  test    eax, eax
0x140016378  jns     short loc_14001638E
0x14001637a  mov     r9d, eax
0x14001637d  lea     r8, aFailedToOpenIn; "Failed to open interface key."
0x140016384  mov     edx, 848h
0x140016389  jmp     loc_140016555
0x14001638e  lea     rax, [rsp+8D0h+var_8A0+4]
0x140016393  mov     dword ptr [rsp+8D0h+var_8A0+4], r14d
0x140016398  mov     [rsp+8D0h+ResultLength], rax; ResultLength
0x14001639d  lea     r9, [rsp+8D0h+KeyValueInformation]; KeyValueInformation
0x1400163a2  mov     r8d, 2; KeyValueInformationClass
0x1400163a8  mov     [rsp+8D0h+Length], 410h; Length
0x1400163b0  lea     rdx, [rsp+8D0h+DestinationString]; ValueName
0x1400163b5  mov     rcx, r15; KeyHandle
0x1400163b8  call    cs:__imp_NtQueryValueKey
0x1400163be  mov     ebx, eax
0x1400163c0  mov     eax, 0C0000034h
0x1400163c5  cmp     ebx, eax
0x1400163c7  jnz     short loc_1400163DD
0x1400163c9  mov     r9d, eax
0x1400163cc  lea     r8, aSecurekerneltr_1; "SecureKernelTrustlet registry key not f"...
0x1400163d3  mov     edx, 857h
0x1400163d8  jmp     loc_140016555
0x1400163dd  cmp     ebx, 80000005h
0x1400163e3  jz      loc_140016546
0x1400163e9  cmp     ebx, 0C0000023h
0x1400163ef  jz      loc_140016546
0x1400163f5  test    ebx, ebx
0x1400163f7  jns     short loc_14001640A
0x1400163f9  lea     r8, aFailedToQueryS; "Failed to query SecureKernelTrustlet re"...
0x140016400  mov     edx, 864h
0x140016405  jmp     loc_140016552
0x14001640a  cmp     [rsp+8D0h+var_85C], 1
0x14001640f  jz      short loc_140016428
0x140016411  mov     r9d, 0C0000024h
0x140016417  lea     r8, aSecurekerneltr_0; "SecureKernelTrustlet registry value is "...
0x14001641e  mov     edx, 86Ch
0x140016423  jmp     loc_140016555
0x140016428  movzx   r14d, word ptr [rsp+8D0h+var_858]
0x14001642e  add     r14w, [rsp+8D0h+SourceString.Length]
0x140016434  cmp     r14w, [rsp+8D0h+SourceString.Length]
0x14001643a  jb      loc_140016527
0x140016440  movzx   eax, r14w
0x140016444  cmp     eax, [rsp+8D0h+var_858]
0x140016448  jb      loc_140016527
0x14001644e  mov     byte ptr [r13+0], 1
0x140016453  xor     edx, edx; Flags
0x140016455  mov     rcx, gs:60h
0x14001645e  movzx   r8d, r14w; Size
0x140016462  mov     rcx, [rcx+30h]; HeapHandle
0x140016466  call    cs:__imp_RtlAllocateHeap
0x14001646c  mov     [rsp+8D0h+var_898.Buffer], rax
0x140016471  test    rax, rax
0x140016474  jnz     short loc_14001648D
0x140016476  mov     r9d, 0C000009Ah
0x14001647c  lea     r8, aFailedToAlloca; "Failed to allocate memory for trustlet "...
0x140016483  mov     edx, 882h
0x140016488  jmp     loc_140016539
0x14001648d  xor     eax, eax
0x14001648f  mov     [rsp+8D0h+var_898.MaximumLength], r14w
0x140016495  lea     rdx, [rsp+8D0h+SourceString]; SourceString
0x14001649a  mov     [rsp+8D0h+var_898.Length], ax
0x14001649f  lea     rcx, [rsp+8D0h+var_898]; DestinationString
0x1400164a4  call    RtlUnicodeStringCat
0x1400164a9  xor     r14d, r14d
0x1400164ac  mov     ebx, eax
0x1400164ae  test    eax, eax
0x1400164b0  jns     short loc_1400164CB
0x1400164b2  lea     r8, aFailedToAddPre; "Failed to add prefix to trustlet path."
0x1400164b9  mov     edx, 88Dh
0x1400164be  mov     r9d, eax
0x1400164c1  mov     rcx, rsi
0x1400164c4  call    SmpLogFailureString
0x1400164c9  jmp     short loc_140016504
0x1400164cb  lea     rdx, [rsp+8D0h+pszSrc]; pszSrc
0x1400164d0  lea     rcx, [rsp+8D0h+var_898]; DestinationString
0x1400164d5  call    RtlUnicodeStringCatString
0x1400164da  mov     ebx, eax
0x1400164dc  test    eax, eax
0x1400164de  jns     short loc_1400164EE
0x1400164e0  lea     r8, aFailedToAppend; "Failed to append registry data to trust"...
0x1400164e7  mov     edx, 895h
0x1400164ec  jmp     short loc_1400164BE
0x1400164ee  xor     r9d, r9d
0x1400164f1  mov     qword ptr [rsp+8D0h+Length], r14
0x1400164f6  xor     edx, edx
0x1400164f8  lea     rcx, [rsp+8D0h+var_898]
0x1400164fd  call    SmpExecuteCommand
0x140016502  mov     ebx, eax
0x140016504  cmp     [rsp+8D0h+var_898.Buffer], r14
0x140016509  jz      short loc_14001655D
0x14001650b  mov     rcx, gs:60h
0x140016514  xor     edx, edx; Flags
0x140016516  mov     r8, [rsp+8D0h+var_898.Buffer]; BaseAddress
0x14001651b  mov     rcx, [rcx+30h]; HeapHandle
0x14001651f  call    cs:__imp_RtlFreeHeap
0x140016525  jmp     short loc_14001655D
0x140016527  mov     r9d, 0C000000Dh
0x14001652d  lea     r8, aProvidedTrustl; "Provided trustlet path is too long."
0x140016534  mov     edx, 874h
0x140016539  mov     rcx, rsi
0x14001653c  call    SmpLogFailureString
0x140016541  xor     r14d, r14d
0x140016544  jmp     short loc_14001655D
0x140016546  lea     r8, aRegistryBuffer; "Registry Buffer too small"
0x14001654d  mov     edx, 85Eh
0x140016552  mov     r9d, ebx
0x140016555  mov     rcx, rsi
0x140016558  call    SmpLogFailureString
0x14001655d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016561  inc     rax
0x140016564  cmp     [r12+rax*2], r14w
0x140016569  jnz     short loc_140016561
0x14001656b  lea     r12, [r12+rax*2]
0x14001656f  add     r12, 2
0x140016573  cmp     [r12], r14w
0x140016578  jnz     loc_140016344
0x14001657e  test    r15, r15
0x140016581  jz      short loc_14001658C
0x140016583  mov     rcx, r15; Handle
0x140016586  call    cs:__imp_NtClose
0x14001658c  test    rdi, rdi
0x14001658f  jz      short loc_1400165B5
0x140016591  lea     rax, [rbp+7D0h+BaseAddress]
0x140016598  cmp     rdi, rax
0x14001659b  jz      short loc_1400165B5
0x14001659d  mov     rcx, gs:60h
0x1400165a6  mov     r8, rdi; BaseAddress
0x1400165a9  xor     edx, edx; Flags
0x1400165ab  mov     rcx, [rcx+30h]; HeapHandle
0x1400165af  call    cs:__imp_RtlFreeHeap
0x1400165b5  mov     rcx, cs:NtPnpDeviceApiDriverHandle; Handle
0x1400165bc  test    rcx, rcx
0x1400165bf  jz      short loc_1400165CE
0x1400165c1  call    cs:__imp_NtClose
0x1400165c7  mov     cs:NtPnpDeviceApiDriverHandle, r14
0x1400165ce  mov     eax, ebx
0x1400165d0  mov     rcx, [rbp+7D0h+var_50]
0x1400165d7  xor     rcx, rsp; StackCookie
0x1400165da  call    __security_check_cookie
0x1400165df  add     rsp, 898h
0x1400165e6  pop     r15
0x1400165e8  pop     r14
0x1400165ea  pop     r13
0x1400165ec  pop     r12
0x1400165ee  pop     rdi
0x1400165ef  pop     rsi
0x1400165f0  pop     rbx
0x1400165f1  pop     rbp
0x1400165f2  retn
```
