# SdbpGetManifestedMergeStubAlloc

- ea: `0x14001687c`
- end: `0x140016c92`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1046`
- prototype: `__int64 __fastcall(_QWORD *, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140016c98`

## callees

- `0x140001f94`
- `0x14001008c`
- `0x1400102a0`
- `0x14001031c`
- `0x140010568`
- `0x140010d44`
- `0x14001687c`
- `0x140017498`
- `0x14001759c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140016b40`
- `msvcrt!_wcsnicmp` at `0x140016b40`
- `ntdll!RtlAllocateHeap` at `0x1400169c8`
- `ntdll!RtlAllocateHeap` at `0x140016aa1`
- `ntdll!RtlAllocateHeap` at `0x1400169c8`
- `ntdll!RtlAllocateHeap` at `0x140016aa1`
- `ntdll!RtlFreeHeap` at `0x140016c38`
- `ntdll!RtlFreeHeap` at `0x140016c55`
- `ntdll!RtlFreeHeap` at `0x140016c72`
- `ntdll!RtlFreeHeap` at `0x140016c38`
- `ntdll!RtlFreeHeap` at `0x140016c55`
- `ntdll!RtlFreeHeap` at `0x140016c72`
- `ntdll!ZwClose` at `0x140016c1b`
- `ntdll!ZwClose` at `0x140016c1b`
- `ntdll!ZwEnumerateValueKey` at `0x140016a25`
- `ntdll!ZwEnumerateValueKey` at `0x140016ae0`
- `ntdll!ZwEnumerateValueKey` at `0x140016a25`
- `ntdll!ZwEnumerateValueKey` at `0x140016ae0`

## string_xrefs

- `0x1400168f6`: `SdbpGetManifestedMergeStubAlloc`
- `0x140016950`: `SdbpGetManifestedMergeStubAlloc`
- `0x1400169e9`: `SdbpGetManifestedMergeStubAlloc`
- `0x140016b7e`: `SdbpGetManifestedMergeStubAlloc`
- `0x140016bf0`: `SdbpGetManifestedMergeStubAlloc`
- `0x140016918`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x14001693f`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x140016b71`: `Failed to allocate or convert stub path.`
- `0x140016ba8`: `Failed to duplicate stub path.`
- `0x140016bc5`: `Failed to allocate stub path.`

## pseudocode

```c
__int64 __fastcall SdbpGetManifestedMergeStubAlloc(_QWORD *a1, const wchar_t *a2)
{
  void *v3; // rsi
  int v5; // ebx
  int MergeSdbsDisabled; // eax
  PVOID Heap; // r12
  wchar_t *v8; // r13
  int Key; // eax
  unsigned int v10; // ebx
  __int64 v11; // r14
  __int64 v12; // rax
  ULONG Length; // ebx
  ULONG v14; // r12d
  wchar_t *v15; // rax
  NTSTATUS v16; // eax
  __int64 v17; // rax
  ULONG v18; // ebx
  unsigned __int64 v19; // r15
  const wchar_t *NtSystemRoot; // rax
  const wchar_t *v21; // rbx
  size_t v22; // r8
  const wchar_t *KeyValueInformation; // [rsp+30h] [rbp-20h]
  void *v24; // [rsp+38h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+50h] BYREF
  ULONG v28; // [rsp+A8h] [rbp+58h] BYREF

  v28 = 0;
  v3 = 0;
  ResultLength = 0;
  v24 = 0;
  KeyHandle = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    MergeSdbsDisabled = SdbpGetMergeSdbsDisabled(&v28);
    v5 = MergeSdbsDisabled;
    if ( MergeSdbsDisabled < 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbpGetManifestedMergeStubAlloc",
        1186,
        "SdbpGetMergeSdbsDisabled failed [%x]",
        MergeSdbsDisabled);
      return (unsigned int)v5;
    }
    if ( !v28 )
    {
      Heap = 0;
      v8 = 0;
      Key = AslRegistryGetKey(
              &KeyHandle,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
              0x80000100);
      v5 = Key;
      if ( Key < 0 )
      {
        if ( Key != -1073741772 )
          AslLogCallPrintf(
            1,
            "SdbpGetManifestedMergeStubAlloc",
            1202,
            "AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]",
            Key);
LABEL_52:
        if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          ZwClose(KeyHandle);
        if ( v3 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
        if ( Heap )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        if ( v8 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
        return (unsigned int)v5;
      }
      v10 = 1;
      while ( wcsicmp_0(a2, (const wchar_t *)qword_140030C58[4 * v10]) )
      {
        if ( (int)++v10 >= 10 )
        {
LABEL_51:
          v5 = -1073741772;
          goto LABEL_52;
        }
      }
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      Length = 2 * v12 + 18;
      v28 = Length;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
      KeyValueInformation = (const wchar_t *)Heap;
      if ( !Heap )
      {
        v5 = -1073741801;
        AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1222, "Failed to allocate partial info.");
        goto LABEL_52;
      }
      v14 = 0;
      v15 = (wchar_t *)KeyValueInformation;
      while ( 1 )
      {
        v16 = ZwEnumerateValueKey(KeyHandle, v14, KeyValuePartialInformation, v15, Length, &ResultLength);
        v5 = v16;
        if ( v16 == -2147483643 || v16 == -1073741789 )
          goto LABEL_26;
        if ( v16 == -2147483622 )
        {
          Heap = (PVOID)KeyValueInformation;
          goto LABEL_51;
        }
        if ( v16 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1241, "Failed to query partial info.");
          goto LABEL_49;
        }
        v15 = (wchar_t *)KeyValueInformation;
        if ( *((_DWORD *)KeyValueInformation + 1) == 1 )
          break;
LABEL_27:
        Length = v28;
        ++v14;
      }
      if ( !wcsicmp_0(a2, KeyValueInformation + 6) )
      {
        v17 = -1;
        do
          ++v17;
        while ( a2[v17] );
        v18 = 2 * v17 + 538;
        v19 = v18;
        v8 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v18);
        if ( !v8 )
        {
          v5 = -1073741801;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1258, "Failed to allocate basic info.");
LABEL_49:
          Heap = (PVOID)KeyValueInformation;
          goto LABEL_52;
        }
        v5 = ZwEnumerateValueKey(KeyHandle, v14, KeyValueBasicInformation, v8, v18, &ResultLength);
        if ( v5 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1269, "Failed to query basic info.");
          goto LABEL_49;
        }
        if ( (unsigned __int64)ResultLength + 2 > v19 )
        {
          v5 = -1073741789;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1274, "Buffer too small to query basic info.");
          goto LABEL_49;
        }
        NtSystemRoot = (const wchar_t *)AslPathGetNtSystemRoot();
        v21 = NtSystemRoot;
        v22 = -1;
        do
          ++v22;
        while ( NtSystemRoot[v22] );
        if ( _wcsnicmp(NtSystemRoot, v8 + 6, v22) )
        {
          v5 = AslStringDuplicate(&v24, v8 + 6);
          if ( v5 < 0 )
          {
            AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1301, "Failed to duplicate stub path.");
            goto LABEL_42;
          }
        }
        else
        {
          do
            ++v11;
          while ( v21[v11] );
          v5 = AslPathToSystemPath(&v24, &v8[v11 + 6]);
          if ( v5 < 0 )
          {
            AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1294, "Failed to allocate or convert stub path.");
LABEL_42:
            v3 = v24;
            goto LABEL_49;
          }
        }
        v3 = v24;
        if ( v24 )
        {
          v5 = 0;
          *a1 = v24;
          v3 = 0;
        }
        else
        {
          v5 = -1073741801;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1308, "Failed to allocate stub path.");
        }
        goto LABEL_49;
      }
LABEL_26:
      v15 = (wchar_t *)KeyValueInformation;
      goto LABEL_27;
    }
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x14001687c  mov     [rsp-38h+arg_8], rbx
0x140016881  mov     [rsp-38h+arg_0], rcx
0x140016886  push    rbp
0x140016887  push    rsi
0x140016888  push    rdi
0x140016889  push    r12
0x14001688b  push    r13
0x14001688d  push    r14
0x14001688f  push    r15
0x140016891  mov     rbp, rsp
0x140016894  sub     rsp, 50h
0x140016898  xor     r14d, r14d
0x14001689b  mov     r15, rdx
0x14001689e  mov     [rbp+arg_18], r14d
0x1400168a2  mov     esi, r14d
0x1400168a5  mov     [rbp+arg_10], r14d
0x1400168a9  mov     [rbp+var_18], r14
0x1400168ad  mov     [rbp+KeyHandle], r14
0x1400168b1  test    rcx, rcx
0x1400168b4  jnz     short loc_1400168C0
0x1400168b6  mov     eax, 0C00000EFh
0x1400168bb  jmp     loc_140016C7A
0x1400168c0  mov     [rcx], r14
0x1400168c3  call    SdbpGetMergeSdbsSupported
0x1400168c8  test    eax, eax
0x1400168ca  jnz     short loc_1400168D6
0x1400168cc  mov     ebx, 0C0000034h
0x1400168d1  jmp     loc_140016C78
0x1400168d6  lea     rcx, [rbp+arg_18]
0x1400168da  call    SdbpGetMergeSdbsDisabled
0x1400168df  mov     ebx, eax
0x1400168e1  test    eax, eax
0x1400168e3  jns     short loc_14001690C
0x1400168e5  lea     r9, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled failed [%x]"
0x1400168ec  mov     [rsp+50h+Length], eax
0x1400168f0  mov     r8d, 4A2h
0x1400168f6  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1400168fd  mov     ecx, 1
0x140016902  call    AslLogCallPrintf
0x140016907  jmp     loc_140016C78
0x14001690c  cmp     [rbp+arg_18], r14d
0x140016910  jnz     short loc_1400168CC
0x140016912  mov     r8d, 80000100h
0x140016918  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001691f  lea     rcx, [rbp+KeyHandle]
0x140016923  mov     r12, r14
0x140016926  mov     r13, r14
0x140016929  call    AslRegistryGetKey
0x14001692e  mov     ebx, eax
0x140016930  test    eax, eax
0x140016932  jns     short loc_140016966
0x140016934  cmp     eax, 0C0000034h
0x140016939  jz      loc_140016C0D
0x14001693f  lea     r9, aAslregistryget_2; "AslRegistryGetKey failed to open Manife"...
0x140016946  mov     [rsp+50h+Length], eax
0x14001694a  mov     r8d, 4B2h
0x140016950  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x140016957  mov     ecx, 1
0x14001695c  call    AslLogCallPrintf
0x140016961  jmp     loc_140016C0D
0x140016966  mov     edi, 1
0x14001696b  mov     ebx, edi
0x14001696d  lea     rax, qword_140030C58
0x140016974  mov     edx, ebx
0x140016976  shl     rdx, 5
0x14001697a  mov     rcx, r15; String1
0x14001697d  mov     rdx, [rdx+rax]; String2
0x140016981  call    _wcsicmp_0
0x140016986  test    eax, eax
0x140016988  jz      short loc_140016996
0x14001698a  add     ebx, edi
0x14001698c  cmp     ebx, 0Ah
0x14001698f  jl      short loc_14001696D
0x140016991  jmp     loc_140016C08
0x140016996  or      r14, 0FFFFFFFFFFFFFFFFh
0x14001699a  mov     rax, r14
0x14001699d  xor     ecx, ecx
0x14001699f  inc     rax
0x1400169a2  cmp     [r15+rax*2], cx
0x1400169a7  jnz     short loc_14001699F
0x1400169a9  mov     rcx, gs:60h
0x1400169b2  lea     ebx, ds:12h[rax*2]
0x1400169b9  mov     r8d, ebx; Size
0x1400169bc  mov     edx, 8; Flags
0x1400169c1  mov     [rbp+arg_18], ebx
0x1400169c4  mov     rcx, [rcx+30h]; HeapHandle
0x1400169c8  call    cs:__imp_RtlAllocateHeap
0x1400169ce  mov     r12, rax
0x1400169d1  mov     [rbp+KeyValueInformation], rax
0x1400169d5  xor     eax, eax
0x1400169d7  test    r12, r12
0x1400169da  jnz     short loc_140016A01
0x1400169dc  lea     r9, aFailedToAlloca; "Failed to allocate partial info."
0x1400169e3  mov     r8d, 4C6h
0x1400169e9  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1400169f0  mov     ecx, edi
0x1400169f2  mov     ebx, 0C0000017h
0x1400169f7  call    AslLogCallPrintf
0x1400169fc  jmp     loc_140016C0D
0x140016a01  mov     r12d, eax
0x140016a04  mov     rax, [rbp+KeyValueInformation]
0x140016a08  lea     rcx, [rbp+arg_10]
0x140016a0c  mov     r9, rax; KeyValueInformation
0x140016a0f  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x140016a14  mov     r8d, 2; KeyValueInformationClass
0x140016a1a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140016a1e  mov     edx, r12d; Index
0x140016a21  mov     [rsp+50h+Length], ebx; Length
0x140016a25  call    cs:__imp_ZwEnumerateValueKey
0x140016a2b  mov     ebx, eax
0x140016a2d  cmp     eax, 80000005h
0x140016a32  jz      short loc_140016A69
0x140016a34  cmp     eax, 0C0000023h
0x140016a39  jz      short loc_140016A69
0x140016a3b  cmp     eax, 8000001Ah
0x140016a40  jz      loc_140016C04
0x140016a46  test    eax, eax
0x140016a48  js      loc_140016BE3
0x140016a4e  mov     rax, [rbp+KeyValueInformation]
0x140016a52  cmp     [rax+4], edi
0x140016a55  jnz     short loc_140016A6D
0x140016a57  lea     rdx, [rax+0Ch]; String2
0x140016a5b  mov     rcx, r15; String1
0x140016a5e  call    _wcsicmp_0
0x140016a63  xor     ecx, ecx
0x140016a65  test    eax, eax
0x140016a67  jz      short loc_140016A75
0x140016a69  mov     rax, [rbp+KeyValueInformation]
0x140016a6d  mov     ebx, [rbp+arg_18]
0x140016a70  add     r12d, edi
0x140016a73  jmp     short loc_140016A08
0x140016a75  mov     rax, r14
0x140016a78  inc     rax
0x140016a7b  cmp     [r15+rax*2], cx
0x140016a80  jnz     short loc_140016A78
0x140016a82  mov     rcx, gs:60h
0x140016a8b  lea     ebx, ds:21Ah[rax*2]
0x140016a92  mov     r8d, ebx; Size
0x140016a95  mov     edx, 8; Flags
0x140016a9a  mov     r15d, ebx
0x140016a9d  mov     rcx, [rcx+30h]; HeapHandle
0x140016aa1  call    cs:__imp_RtlAllocateHeap
0x140016aa7  mov     r13, rax
0x140016aaa  test    rax, rax
0x140016aad  jnz     short loc_140016AC6
0x140016aaf  mov     ebx, 0C0000017h
0x140016ab4  lea     r9, aFailedToAlloca_6; "Failed to allocate basic info."
0x140016abb  mov     r8d, 4EAh
0x140016ac1  jmp     loc_140016BF0
0x140016ac6  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140016aca  lea     rax, [rbp+arg_10]
0x140016ace  mov     [rsp+50h+ResultLength], rax; ResultLength
0x140016ad3  mov     r9, r13; KeyValueInformation
0x140016ad6  xor     r8d, r8d; KeyValueInformationClass
0x140016ad9  mov     [rsp+50h+Length], ebx; Length
0x140016add  mov     edx, r12d; Index
0x140016ae0  call    cs:__imp_ZwEnumerateValueKey
0x140016ae6  xor     r12d, r12d
0x140016ae9  mov     ebx, eax
0x140016aeb  test    eax, eax
0x140016aed  jns     short loc_140016B01
0x140016aef  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x140016af6  mov     r8d, 4F5h
0x140016afc  jmp     loc_140016BF0
0x140016b01  mov     eax, [rbp+arg_10]
0x140016b04  add     rax, 2
0x140016b08  cmp     rax, r15
0x140016b0b  jbe     short loc_140016B24
0x140016b0d  mov     ebx, 0C0000023h
0x140016b12  lea     r9, aBufferTooSmall_0; "Buffer too small to query basic info."
0x140016b19  mov     r8d, 4FAh
0x140016b1f  jmp     loc_140016BF0
0x140016b24  call    AslPathGetNtSystemRoot
0x140016b29  mov     rbx, rax
0x140016b2c  mov     r8, r14
0x140016b2f  inc     r8; MaxCount
0x140016b32  cmp     [rax+r8*2], r12w
0x140016b37  jnz     short loc_140016B2F
0x140016b39  lea     rdx, [r13+0Ch]; String2
0x140016b3d  mov     rcx, rbx; String1
0x140016b40  call    cs:__imp__wcsnicmp
0x140016b46  test    eax, eax
0x140016b48  jnz     short loc_140016B92
0x140016b4a  inc     r14
0x140016b4d  cmp     [rbx+r14*2], r12w
0x140016b52  jnz     short loc_140016B4A
0x140016b54  lea     rdx, ds:0Ch[r14*2]
0x140016b5c  add     rdx, r13
0x140016b5f  lea     rcx, [rbp+var_18]
0x140016b63  call    AslPathToSystemPath
0x140016b68  xor     r14d, r14d
0x140016b6b  mov     ebx, eax
0x140016b6d  test    eax, eax
0x140016b6f  jns     short loc_140016BB7
0x140016b71  lea     r9, aFailedToAlloca_2; "Failed to allocate or convert stub path"...
0x140016b78  mov     r8d, 50Eh
0x140016b7e  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x140016b85  mov     ecx, edi
0x140016b87  call    AslLogCallPrintf
0x140016b8c  mov     rsi, [rbp+var_18]
0x140016b90  jmp     short loc_140016BFE
0x140016b92  lea     rdx, [r13+0Ch]
0x140016b96  lea     rcx, [rbp+var_18]
0x140016b9a  call    AslStringDuplicate
0x140016b9f  xor     r14d, r14d
0x140016ba2  mov     ebx, eax
0x140016ba4  test    eax, eax
0x140016ba6  jns     short loc_140016BB7
0x140016ba8  lea     r9, aFailedToDuplic_0; "Failed to duplicate stub path."
0x140016baf  mov     r8d, 515h
0x140016bb5  jmp     short loc_140016B7E
0x140016bb7  mov     rsi, [rbp+var_18]
0x140016bbb  test    rsi, rsi
0x140016bbe  jnz     short loc_140016BD4
0x140016bc0  mov     ebx, 0C0000017h
0x140016bc5  lea     r9, aFailedToAlloca_9; "Failed to allocate stub path."
0x140016bcc  mov     r8d, 51Ch
0x140016bd2  jmp     short loc_140016BF0
0x140016bd4  mov     rax, [rbp+arg_0]
0x140016bd8  mov     ebx, r14d
0x140016bdb  mov     [rax], rsi
0x140016bde  mov     rsi, r14
0x140016be1  jmp     short loc_140016BFE
0x140016be3  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x140016bea  mov     r8d, 4D9h
0x140016bf0  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x140016bf7  mov     ecx, edi
0x140016bf9  call    AslLogCallPrintf
0x140016bfe  mov     r12, [rbp+KeyValueInformation]
0x140016c02  jmp     short loc_140016C0D
0x140016c04  mov     r12, [rbp+KeyValueInformation]
0x140016c08  mov     ebx, 0C0000034h
0x140016c0d  mov     rcx, [rbp+KeyHandle]; Handle
0x140016c11  lea     rax, [rcx-1]
0x140016c15  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140016c19  ja      short loc_140016C21
0x140016c1b  call    cs:__imp_ZwClose
0x140016c21  test    rsi, rsi
0x140016c24  jz      short loc_140016C3E
0x140016c26  mov     rcx, gs:60h
0x140016c2f  mov     r8, rsi; P
0x140016c32  xor     edx, edx; Flags
0x140016c34  mov     rcx, [rcx+30h]; HeapHandle
0x140016c38  call    cs:__imp_RtlFreeHeap
0x140016c3e  test    r12, r12
0x140016c41  jz      short loc_140016C5B
0x140016c43  mov     rcx, gs:60h
0x140016c4c  mov     r8, r12; P
0x140016c4f  xor     edx, edx; Flags
0x140016c51  mov     rcx, [rcx+30h]; HeapHandle
0x140016c55  call    cs:__imp_RtlFreeHeap
0x140016c5b  test    r13, r13
0x140016c5e  jz      short loc_140016C78
0x140016c60  mov     rcx, gs:60h
0x140016c69  mov     r8, r13; P
0x140016c6c  xor     edx, edx; Flags
0x140016c6e  mov     rcx, [rcx+30h]; HeapHandle
0x140016c72  call    cs:__imp_RtlFreeHeap
0x140016c78  mov     eax, ebx
0x140016c7a  mov     rbx, [rsp+50h+arg_8]
0x140016c82  add     rsp, 50h
0x140016c86  pop     r15
0x140016c88  pop     r14
0x140016c8a  pop     r13
0x140016c8c  pop     r12
0x140016c8e  pop     rdi
0x140016c8f  pop     rsi
0x140016c90  pop     rbp
0x140016c91  retn
```
