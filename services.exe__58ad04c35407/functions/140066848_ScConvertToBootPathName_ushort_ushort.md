# ScConvertToBootPathName(ushort *,ushort * *)

- ea: `0x140066848`
- end: `0x140066eee`
- name: `?ScConvertToBootPathName@@YAKPEAGPEAPEAG@Z`
- size: `1702`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400661a0`
- `0x140068b60`

## callees

- `0x140004c58`
- `0x140008b90`
- `0x14000ff90`
- `0x1400188fc`
- `0x14001df34`
- `0x14001f99c`
- `0x14004af50`
- `0x140066848`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140066a6f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140066aec`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140066a6f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140066aec`
- `ntdll!RtlFreeUnicodeString` at `0x140066edf`
- `ntdll!RtlFreeUnicodeString` at `0x140066edf`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x140066b53`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x140066b53`
- `ntdll!NtClose` at `0x140066ebc`
- `ntdll!NtClose` at `0x140066ebc`
- `ntdll!RtlInitUnicodeString` at `0x140066cd8`
- `ntdll!RtlInitUnicodeString` at `0x140066cd8`
- `ntdll!RtlFreeHeap` at `0x140066b3e`
- `ntdll!RtlFreeHeap` at `0x140066b6f`
- `ntdll!RtlFreeHeap` at `0x140066b95`
- `ntdll!RtlFreeHeap` at `0x140066ed5`
- `ntdll!RtlFreeHeap` at `0x140066b3e`
- `ntdll!RtlFreeHeap` at `0x140066b6f`
- `ntdll!RtlFreeHeap` at `0x140066b95`
- `ntdll!RtlFreeHeap` at `0x140066ed5`
- `ntdll!NtQuerySymbolicLinkObject` at `0x140066d31`
- `ntdll!NtQuerySymbolicLinkObject` at `0x140066dfd`
- `ntdll!NtQuerySymbolicLinkObject` at `0x140066d31`
- `ntdll!NtQuerySymbolicLinkObject` at `0x140066dfd`
- `ntdll!NtOpenSymbolicLinkObject` at `0x140066d11`
- `ntdll!NtOpenSymbolicLinkObject` at `0x140066d11`
- `ntdll!RtlAllocateHeap` at `0x1400668e6`
- `ntdll!RtlAllocateHeap` at `0x14006696d`
- `ntdll!RtlAllocateHeap` at `0x1400669fe`
- `ntdll!RtlAllocateHeap` at `0x140066a9a`
- `ntdll!RtlAllocateHeap` at `0x140066bc0`
- `ntdll!RtlAllocateHeap` at `0x140066c64`
- `ntdll!RtlAllocateHeap` at `0x140066da4`
- `ntdll!RtlAllocateHeap` at `0x140066e4f`
- `ntdll!RtlAllocateHeap` at `0x1400668e6`
- `ntdll!RtlAllocateHeap` at `0x14006696d`
- `ntdll!RtlAllocateHeap` at `0x1400669fe`
- `ntdll!RtlAllocateHeap` at `0x140066a9a`
- `ntdll!RtlAllocateHeap` at `0x140066bc0`
- `ntdll!RtlAllocateHeap` at `0x140066c64`
- `ntdll!RtlAllocateHeap` at `0x140066da4`
- `ntdll!RtlAllocateHeap` at `0x140066e4f`

## string_xrefs

- `0x140066941`: `System32\`

## pseudocode

```c
__int64 __fastcall ScConvertToBootPathName(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int64 v2; // rdi
  unsigned int v5; // ebx
  SIZE_T v6; // r8
  unsigned __int64 v7; // rdi
  unsigned __int16 *Heap; // rax
  PRPC_ASYNC_STATE v9; // rcx
  __int64 v10; // rdx
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // r8
  unsigned __int16 *v14; // rax
  DWORD v15; // eax
  DWORD v16; // r13d
  DWORD v17; // r12d
  WCHAR *v18; // rax
  WCHAR *v19; // r15
  WCHAR *v20; // r8
  BOOLEAN v21; // al
  PVOID ProcessHeap; // rcx
  unsigned __int64 v23; // r12
  unsigned __int16 *v24; // rax
  PRPC_ASYNC_STATE v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  const wchar_t *v28; // r10
  __int64 v29; // rdi
  int v30; // r13d
  unsigned __int64 v31; // rdi
  unsigned __int16 *v32; // rax
  const unsigned __int16 *v33; // r8
  NTSTATUS v34; // eax
  unsigned int v35; // r15d
  __int64 v36; // r12
  __int64 v37; // rdi
  int v38; // r15d
  unsigned __int16 *v39; // rax
  void *SymbolicLinkHandle; // [rsp+20h] [rbp-49h] BYREF
  unsigned __int16 *v41; // [rsp+28h] [rbp-41h]
  struct _UNICODE_STRING LinkTarget; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  WCHAR Dst; // [rsp+E0h] [rbp+77h] BYREF
  ULONG DataWritten; // [rsp+E8h] [rbp+7Fh] BYREF

  Dst = 0;
  NtPathName = 0;
  SymbolicLinkHandle = 0;
  v2 = -1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_QWORD *)&LinkTarget.Length = 0;
  LinkTarget.Buffer = 0;
  DataWritten = 0;
  DestinationString = 0;
  do
    ++v2;
  while ( a1[v2] );
  v5 = 8;
  if ( (unsigned int)v2 <= 0xC )
  {
    if ( (unsigned int)v2 <= 9 )
      goto LABEL_27;
  }
  else if ( !wcsnicmp(L"\\SystemRoot\\", a1, 0xCu) )
  {
    v6 = 2LL * (unsigned int)(v2 + 1);
    v7 = (unsigned int)(v2 + 1);
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    *a2 = Heap;
    if ( !Heap )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        return v5;
      v10 = 101;
      goto LABEL_25;
    }
    StringCchCopyW(Heap, v7, a1);
    return 0;
  }
  if ( !wcsnicmp(L"System32\\", a1, 9u) )
  {
    v2 = (unsigned int)v2 + 13LL;
    v12 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v2);
    *a2 = v12;
    if ( !v12 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        return v5;
      v10 = 102;
      goto LABEL_25;
    }
    StringCchCopyW(v12, v2, L"\\SystemRoot\\");
    v13 = a1;
    goto LABEL_18;
  }
  if ( (unsigned int)v2 > 0xD && !wcsnicmp(L"%SystemRoot%\\", a1, 0xDu) )
  {
    v2 = (unsigned int)v2;
    v14 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * (unsigned int)v2);
    *a2 = v14;
    if ( !v14 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        return v5;
      v10 = 103;
LABEL_25:
      WPP_SF_(v9->StubInfo, v10, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
      return v5;
    }
    StringCchCopyW(v14, (unsigned int)v2, L"\\SystemRoot\\");
    v13 = a1 + 13;
LABEL_18:
    StringCchCatW(*a2, v2, v13);
    return 0;
  }
LABEL_27:
  v15 = ExpandEnvironmentStringsW(L"%SystemRoot%\\", &Dst, 1u);
  v16 = v15;
  if ( v15 > 1 )
  {
    v17 = v15 + 1;
    v18 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (v15 + 1));
    v19 = v18;
    if ( !v18 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 104, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v17);
      return v5;
    }
    if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\", v18, v16) > v16 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 105, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, L"%SystemRoot%\\");
      v20 = v19;
LABEL_38:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      return v5;
    }
    v21 = RtlDosPathNameToNtPathName_U(v19, &NtPathName, 0, 0);
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    if ( !v21 )
    {
      RtlFreeHeap(ProcessHeap, 0, v19);
      return 1805;
    }
    RtlFreeHeap(ProcessHeap, 0, v19);
    v23 = NtPathName.Length >> 1;
    v24 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, NtPathName.Length + 2LL);
    v41 = v24;
    if ( !v24 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_77;
      v26 = 106;
      v27 = (unsigned int)NtPathName.Length + 2;
      goto LABEL_46;
    }
    StringCchCopyNW(v24, (unsigned int)(v23 + 1), NtPathName.Buffer, v23);
    if ( (unsigned int)v2 > (unsigned int)v23 && !wcsnicmp(v28, a1, v23) )
    {
      v29 = (unsigned int)(v2 - v23);
      v30 = v29;
      v31 = v29 + 13;
      v32 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v31);
      *a2 = v32;
      if ( !v32 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_77;
        }
        v27 = (unsigned int)(2 * v30 + 26);
        v26 = 107;
        goto LABEL_46;
      }
      StringCchCopyW(v32, v31, L"\\SystemRoot\\");
      v33 = &a1[v23];
LABEL_54:
      StringCchCatW(*a2, v31, v33);
      v5 = 0;
LABEL_78:
      if ( SymbolicLinkHandle )
        NtClose(SymbolicLinkHandle);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
      RtlFreeUnicodeString(&NtPathName);
      v20 = v41;
      goto LABEL_38;
    }
    RtlInitUnicodeString(&DestinationString, L"\\SystemRoot");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) >= 0 )
    {
      v34 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
      if ( (int)(v34 + 0x80000000) < 0 || v34 == -1073741789 )
      {
        if ( DataWritten > 0xFFFD )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 108, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, DataWritten);
          }
          v5 = 13;
          goto LABEL_77;
        }
        LinkTarget.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, DataWritten + 2LL);
        if ( !LinkTarget.Buffer )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_77;
          }
          v27 = DataWritten;
          v26 = 109;
          goto LABEL_46;
        }
        LinkTarget.Length = DataWritten;
        LinkTarget.MaximumLength = DataWritten + 2;
        if ( NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten) >= 0 )
        {
          v35 = LinkTarget.Length >> 1;
          if ( (unsigned int)v2 <= v35 || (v36 = v35, wcsnicmp(LinkTarget.Buffer, a1, v35)) )
          {
            v5 = 87;
            goto LABEL_77;
          }
          v37 = (unsigned int)v2 - v35;
          v38 = v37;
          v31 = v37 + 13;
          v39 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v31);
          *a2 = v39;
          if ( v39 )
          {
            StringCchCopyW(v39, v31, L"\\SystemRoot\\");
            v33 = &a1[v36 + 1];
            goto LABEL_54;
          }
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_77;
          }
          v27 = (unsigned int)(2 * v38 + 26);
          v26 = 110;
LABEL_46:
          WPP_SF_d(v25->StubInfo, v26, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v27);
LABEL_77:
          *a2 = 0;
          goto LABEL_78;
        }
      }
    }
    v5 = 1805;
    goto LABEL_77;
  }
  return 1805;
}

```

## disassembly

```asm
0x140066848  mov     [rsp-8+arg_0], rbx
0x14006684d  push    rbp
0x14006684e  push    rsi
0x14006684f  push    rdi
0x140066850  push    r12
0x140066852  push    r13
0x140066854  push    r14
0x140066856  push    r15
0x140066858  lea     rbp, [rsp-27h]
0x14006685d  sub     rsp, 90h
0x140066864  xor     r15d, r15d
0x140066867  xorps   xmm1, xmm1
0x14006686a  xorps   xmm0, xmm0
0x14006686d  mov     [rbp+57h+Dst], r15w
0x140066872  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x140066876  mov     [rbp+57h+SymbolicLinkHandle], r15
0x14006687a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14006687e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x140066882  mov     qword ptr [rbp+57h+LinkTarget.Length], r15
0x140066886  mov     r14, rdx
0x140066889  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14006688d  mov     [rbp+57h+LinkTarget.Buffer], r15
0x140066891  mov     rsi, rcx
0x140066894  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x140066898  mov     [rbp+57h+DataWritten], r15d
0x14006689c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400668a0  inc     rdi
0x1400668a3  cmp     [rcx+rdi*2], r15w
0x1400668a8  jnz     short loc_1400668A0
0x1400668aa  mov     ebx, 8
0x1400668af  lea     r12, aSystemroot_0; "\\SystemRoot\\"
0x1400668b6  lea     r8d, [rbx+4]; MaxCount
0x1400668ba  cmp     edi, r8d
0x1400668bd  jbe     short loc_140066932
0x1400668bf  mov     rdx, rsi; String2
0x1400668c2  mov     rcx, r12; String1
0x1400668c5  call    _wcsnicmp
0x1400668ca  test    eax, eax
0x1400668cc  jnz     short loc_14006693B
0x1400668ce  mov     rcx, gs:60h
0x1400668d7  lea     eax, [rdi+1]
0x1400668da  lea     r8, [rax+rax]; Size
0x1400668de  mov     edi, eax
0x1400668e0  xor     edx, edx; Flags
0x1400668e2  mov     rcx, [rcx+30h]; HeapHandle
0x1400668e6  call    cs:__imp_RtlAllocateHeap
0x1400668ec  mov     [r14], rax
0x1400668ef  test    rax, rax
0x1400668f2  jnz     short loc_14006691D
0x1400668f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400668fb  lea     rax, WPP_GLOBAL_Control
0x140066902  cmp     rcx, rax
0x140066905  jz      loc_140066AD8
0x14006690b  test    byte ptr [rcx+1Ch], 1
0x14006690f  jz      loc_140066AD8
0x140066915  lea     edx, [rbx+5Dh]
0x140066918  jmp     loc_140066A32
0x14006691d  mov     r8, rsi; unsigned __int16 *
0x140066920  mov     rdx, rdi; unsigned __int64
0x140066923  mov     rcx, rax; unsigned __int16 *
0x140066926  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14006692b  xor     eax, eax
0x14006692d  jmp     loc_140066B7A
0x140066932  cmp     edi, 9
0x140066935  jbe     loc_140066A5E
0x14006693b  mov     r8d, 9; MaxCount
0x140066941  lea     rcx, aSystem32; "System32\\"
0x140066948  mov     rdx, rsi; String2
0x14006694b  call    _wcsnicmp
0x140066950  test    eax, eax
0x140066952  jnz     short loc_1400669C7
0x140066954  mov     rcx, gs:60h
0x14006695d  xor     edx, edx; Flags
0x14006695f  mov     edi, edi
0x140066961  add     rdi, 0Dh
0x140066965  mov     rcx, [rcx+30h]; HeapHandle
0x140066969  lea     r8, [rdi+rdi]; Size
0x14006696d  call    cs:__imp_RtlAllocateHeap
0x140066973  mov     [r14], rax
0x140066976  test    rax, rax
0x140066979  jnz     short loc_1400669A6
0x14006697b  mov     rcx, cs:WPP_GLOBAL_Control
0x140066982  lea     rax, WPP_GLOBAL_Control
0x140066989  cmp     rcx, rax
0x14006698c  jz      loc_140066AD8
0x140066992  test    byte ptr [rcx+1Ch], 1
0x140066996  jz      loc_140066AD8
0x14006699c  mov     edx, 66h ; 'f'
0x1400669a1  jmp     loc_140066A32
0x1400669a6  mov     r8, r12; unsigned __int16 *
0x1400669a9  mov     rdx, rdi; unsigned __int64
0x1400669ac  mov     rcx, rax; unsigned __int16 *
0x1400669af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400669b4  mov     r8, rsi; unsigned __int16 *
0x1400669b7  mov     rcx, [r14]; unsigned __int16 *
0x1400669ba  mov     rdx, rdi; unsigned __int64
0x1400669bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400669c2  jmp     loc_14006692B
0x1400669c7  cmp     edi, 0Dh
0x1400669ca  jbe     loc_140066A5E
0x1400669d0  mov     r8d, 0Dh; MaxCount
0x1400669d6  lea     rcx, aSystemroot_1; "%SystemRoot%\\"
0x1400669dd  mov     rdx, rsi; String2
0x1400669e0  call    _wcsnicmp
0x1400669e5  test    eax, eax
0x1400669e7  jnz     short loc_140066A5E
0x1400669e9  mov     rcx, gs:60h
0x1400669f2  xor     edx, edx; Flags
0x1400669f4  mov     edi, edi
0x1400669f6  mov     rcx, [rcx+30h]; HeapHandle
0x1400669fa  lea     r8, [rdi+rdi]; Size
0x1400669fe  call    cs:__imp_RtlAllocateHeap
0x140066a04  mov     [r14], rax
0x140066a07  test    rax, rax
0x140066a0a  jnz     short loc_140066A47
0x140066a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140066a13  lea     rax, WPP_GLOBAL_Control
0x140066a1a  cmp     rcx, rax
0x140066a1d  jz      loc_140066AD8
0x140066a23  test    byte ptr [rcx+1Ch], 1
0x140066a27  jz      loc_140066AD8
0x140066a2d  mov     edx, 67h ; 'g'
0x140066a32  mov     rcx, [rcx+10h]
0x140066a36  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140066a3d  call    WPP_SF_
0x140066a42  jmp     loc_140066AD8
0x140066a47  mov     r8, r12; unsigned __int16 *
0x140066a4a  mov     rdx, rdi; unsigned __int64
0x140066a4d  mov     rcx, rax; unsigned __int16 *
0x140066a50  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140066a55  lea     r8, [rsi+1Ah]
0x140066a59  jmp     loc_1400669B7
0x140066a5e  mov     r8d, 1; nSize
0x140066a64  lea     rdx, [rbp+57h+Dst]; lpDst
0x140066a68  lea     rcx, aSystemroot_1; "%SystemRoot%\\"
0x140066a6f  call    cs:__imp_ExpandEnvironmentStringsW
0x140066a75  mov     r13d, eax
0x140066a78  cmp     eax, 1
0x140066a7b  jbe     loc_140066B75
0x140066a81  mov     rcx, gs:60h
0x140066a8a  lea     r12d, [rax+1]
0x140066a8e  mov     r8d, r12d
0x140066a91  mov     edx, ebx; Flags
0x140066a93  add     r8, r8; Size
0x140066a96  mov     rcx, [rcx+30h]; HeapHandle
0x140066a9a  call    cs:__imp_RtlAllocateHeap
0x140066aa0  mov     r15, rax
0x140066aa3  test    rax, rax
0x140066aa6  jnz     short loc_140066ADF
0x140066aa8  mov     rcx, cs:WPP_GLOBAL_Control
0x140066aaf  lea     rax, WPP_GLOBAL_Control
0x140066ab6  cmp     rcx, rax
0x140066ab9  jz      short loc_140066AD8
0x140066abb  test    byte ptr [rcx+1Ch], 1
0x140066abf  jz      short loc_140066AD8
0x140066ac1  mov     rcx, [rcx+10h]
0x140066ac5  lea     edx, [r15+68h]
0x140066ac9  mov     r9d, r12d
0x140066acc  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140066ad3  call    WPP_SF_d
0x140066ad8  mov     eax, ebx
0x140066ada  jmp     loc_140066B7A
0x140066adf  mov     r8d, r13d; nSize
0x140066ae2  lea     rcx, aSystemroot_1; "%SystemRoot%\\"
0x140066ae9  mov     rdx, r15; lpDst
0x140066aec  call    cs:__imp_ExpandEnvironmentStringsW
0x140066af2  cmp     eax, r13d
0x140066af5  jbe     short loc_140066B46
0x140066af7  mov     rcx, cs:WPP_GLOBAL_Control
0x140066afe  lea     rax, WPP_GLOBAL_Control
0x140066b05  cmp     rcx, rax
0x140066b08  jz      short loc_140066B2C
0x140066b0a  test    byte ptr [rcx+1Ch], 1
0x140066b0e  jz      short loc_140066B2C
0x140066b10  mov     rcx, [rcx+10h]
0x140066b14  lea     r9, aSystemroot_1; "%SystemRoot%\\"
0x140066b1b  mov     edx, 69h ; 'i'
0x140066b20  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140066b27  call    WPP_SF_S
0x140066b2c  mov     r8, r15; P
0x140066b2f  mov     rcx, gs:60h
0x140066b38  xor     edx, edx; Flags
0x140066b3a  mov     rcx, [rcx+30h]; HeapHandle
0x140066b3e  call    cs:__imp_RtlFreeHeap
0x140066b44  jmp     short loc_140066AD8
0x140066b46  xor     r9d, r9d; DirectoryInfo
0x140066b49  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x140066b4d  xor     r8d, r8d; NtFileNamePart
0x140066b50  mov     rcx, r15; DosPathName
0x140066b53  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x140066b59  mov     rcx, gs:60h
0x140066b62  xor     edx, edx; Flags
0x140066b64  mov     r8, r15; P
0x140066b67  mov     rcx, [rcx+30h]; HeapHandle
0x140066b6b  test    al, al
0x140066b6d  jnz     short loc_140066B95
0x140066b6f  call    cs:__imp_RtlFreeHeap
0x140066b75  mov     eax, 70Dh
0x140066b7a  mov     rbx, [rsp+0C0h+arg_0]
0x140066b82  add     rsp, 90h
0x140066b89  pop     r15
0x140066b8b  pop     r14
0x140066b8d  pop     r13
0x140066b8f  pop     r12
0x140066b91  pop     rdi
0x140066b92  pop     rsi
0x140066b93  pop     rbp
0x140066b94  retn
0x140066b95  call    cs:__imp_RtlFreeHeap
0x140066b9b  mov     rcx, gs:60h
0x140066ba4  mov     r13d, 2
0x140066baa  movzx   r8d, [rbp+57h+NtPathName.Length]
0x140066baf  mov     edx, ebx; Flags
0x140066bb1  movzx   r12d, [rbp+57h+NtPathName.Length]
0x140066bb6  add     r8, r13; Size
0x140066bb9  shr     r12d, 1
0x140066bbc  mov     rcx, [rcx+30h]; HeapHandle
0x140066bc0  call    cs:__imp_RtlAllocateHeap
0x140066bc6  mov     [rbp+57h+var_98], rax
0x140066bca  mov     r10, rax
0x140066bcd  test    rax, rax
0x140066bd0  jnz     short loc_140066C14
0x140066bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140066bd9  lea     rax, WPP_GLOBAL_Control
0x140066be0  cmp     rcx, rax
0x140066be3  jz      loc_140066EAC
0x140066be9  test    byte ptr [rcx+1Ch], 1
0x140066bed  jz      loc_140066EAC
0x140066bf3  movzx   r9d, [rbp+57h+NtPathName.Length]
0x140066bf8  lea     edx, [r13+68h]
0x140066bfc  add     r9d, r13d
0x140066bff  mov     rcx, [rcx+10h]
0x140066c03  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140066c0a  call    WPP_SF_d
0x140066c0f  jmp     loc_140066EAC
0x140066c14  mov     r8, [rbp+57h+NtPathName.Buffer]; unsigned __int16 *
0x140066c18  lea     edx, [r12+1]; unsigned __int64
0x140066c1d  mov     r9, r12; unsigned __int64
0x140066c20  mov     rcx, r10; unsigned __int16 *
0x140066c23  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140066c28  cmp     edi, r12d
0x140066c2b  jbe     loc_140066CCD
0x140066c31  mov     r8, r12; MaxCount
0x140066c34  mov     rdx, rsi; String2
0x140066c37  mov     rcx, r10; String1
0x140066c3a  call    _wcsnicmp
0x140066c3f  test    eax, eax
0x140066c41  jnz     loc_140066CCD
0x140066c47  mov     rcx, gs:60h
0x140066c50  sub     edi, r12d
0x140066c53  mov     r13d, edi
0x140066c56  xor     edx, edx; Flags
0x140066c58  add     rdi, 0Dh
0x140066c5c  mov     rcx, [rcx+30h]; HeapHandle
0x140066c60  lea     r8, [rdi+rdi]; Size
0x140066c64  call    cs:__imp_RtlAllocateHeap
0x140066c6a  mov     [r14], rax
0x140066c6d  test    rax, rax
0x140066c70  jnz     short loc_140066CA5
0x140066c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140066c79  lea     rax, WPP_GLOBAL_Control
0x140066c80  cmp     rcx, rax
0x140066c83  jz      loc_140066EAC
0x140066c89  test    byte ptr [rcx+1Ch], 1
0x140066c8d  jz      loc_140066EAC
0x140066c93  lea     r9d, ds:1Ah[r13*2]
0x140066c9b  mov     edx, 6Bh ; 'k'
0x140066ca0  jmp     loc_140066BFF
0x140066ca5  lea     r8, aSystemroot_0; "\\SystemRoot\\"
0x140066cac  mov     rdx, rdi; unsigned __int64
0x140066caf  mov     rcx, rax; unsigned __int16 *
0x140066cb2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140066cb7  lea     r8, [rsi+r12*2]; unsigned __int16 *
0x140066cbb  mov     rcx, [r14]; unsigned __int16 *
0x140066cbe  mov     rdx, rdi; unsigned __int64
0x140066cc1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140066cc6  xor     ebx, ebx
0x140066cc8  jmp     loc_140066EB3
0x140066ccd  lea     rdx, aSystemroot; "\\SystemRoot"
0x140066cd4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140066cd8  call    cs:__imp_RtlInitUnicodeString
0x140066cde  lea     rax, [rbp+57h+DestinationString]
0x140066ce2  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140066ce9  xorps   xmm0, xmm0
0x140066cec  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140066cf0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140066cf4  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140066cfc  mov     edx, 1; DesiredAccess
0x140066d01  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140066d08  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x140066d0c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140066d11  call    cs:__imp_NtOpenSymbolicLinkObject
0x140066d17  test    eax, eax
0x140066d19  jns     short loc_140066D25
0x140066d1b  mov     ebx, 70Dh
0x140066d20  jmp     loc_140066EAC
0x140066d25  mov     rcx, [rbp+57h+SymbolicLinkHandle]; SymLinkObjHandle
0x140066d29  lea     r8, [rbp+57h+DataWritten]; DataWritten
0x140066d2d  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x140066d31  call    cs:__imp_NtQuerySymbolicLinkObject
  ... truncated ...
```
