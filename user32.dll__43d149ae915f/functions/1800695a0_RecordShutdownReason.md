# RecordShutdownReason

- ea: `0x1800695a0`
- end: `0x180069b61`
- name: `RecordShutdownReason`
- size: `1473`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180077970`

## callees

- `0x180020e80`
- `0x18004c348`
- `0x18004ed44`
- `0x18006081c`
- `0x1800659b0`
- `0x180068b74`
- `0x18006957c`
- `0x1800695a0`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180069b35`
- `ntdll!RtlSetLastWin32Error` at `0x180069b35`
- `ntdll!CsrFreeCaptureBuffer` at `0x18006977f`
- `ntdll!CsrFreeCaptureBuffer` at `0x18006977f`
- `ntdll!wcsrchr` at `0x180069a0a`
- `ntdll!wcsrchr` at `0x180069a31`
- `ntdll!wcsrchr` at `0x180069a0a`
- `ntdll!wcsrchr` at `0x180069a31`
- `ntdll!CsrClientCallServer` at `0x1800699ad`
- `ntdll!CsrClientCallServer` at `0x1800699ad`
- `ntdll!CsrAllocateMessagePointer` at `0x18006981e`
- `ntdll!CsrAllocateMessagePointer` at `0x1800698a3`
- `ntdll!CsrAllocateMessagePointer` at `0x1800698c4`
- `ntdll!CsrAllocateMessagePointer` at `0x18006992a`
- `ntdll!CsrAllocateMessagePointer` at `0x18006981e`
- `ntdll!CsrAllocateMessagePointer` at `0x1800698a3`
- `ntdll!CsrAllocateMessagePointer` at `0x1800698c4`
- `ntdll!CsrAllocateMessagePointer` at `0x18006992a`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180069732`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180069732`
- `ntdll!NtOpenProcessToken` at `0x180069645`
- `ntdll!NtOpenProcessToken` at `0x180069645`
- `ntdll!NtOpenThreadToken` at `0x180069613`
- `ntdll!NtOpenThreadToken` at `0x18006962e`
- `ntdll!NtOpenThreadToken` at `0x180069613`
- `ntdll!NtOpenThreadToken` at `0x18006962e`
- `ntdll!NtClose` at `0x18006966e`
- `ntdll!NtClose` at `0x18006967e`
- `ntdll!NtClose` at `0x18006966e`
- `ntdll!NtClose` at `0x18006967e`
- `ntdll!RtlFreeHeap` at `0x180069796`
- `ntdll!RtlFreeHeap` at `0x1800697a8`
- `ntdll!RtlFreeHeap` at `0x180069796`
- `ntdll!RtlFreeHeap` at `0x1800697a8`
- `ntdll!RtlAllocateHeap` at `0x1800696af`
- `ntdll!RtlAllocateHeap` at `0x180069751`
- `ntdll!RtlAllocateHeap` at `0x1800696af`
- `ntdll!RtlAllocateHeap` at `0x180069751`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800699dd`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800699dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800699ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800699ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800699f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800699f7`
- `KERNELBASE!LoadStringBaseExW` at `0x18006987b`
- `KERNELBASE!LoadStringBaseExW` at `0x18006987b`

## pseudocode

```c
__int64 __fastcall RecordShutdownReason(__int64 a1)
{
  unsigned int v2; // r15d
  __int64 v3; // r14
  NTSTATUS v4; // eax
  ULONG v5; // ecx
  const unsigned __int16 **Heap; // rax
  const unsigned __int16 **v7; // rbx
  const unsigned __int16 *v8; // r12
  const unsigned __int16 *v9; // r13
  ULONG v10; // ecx
  int v11; // r8d
  const unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  struct _CSR_CAPTURE_BUFFER *v16; // r12
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  _OWORD *v20; // rax
  const unsigned __int16 *v21; // rcx
  __int64 v22; // rax
  const unsigned __int16 *v23; // rax
  int v24; // edi
  const WCHAR *v25; // r14
  HANDLE v26; // rax
  void *v27; // rdi
  wchar_t *v28; // rax
  const WCHAR *v29; // rdi
  wchar_t *v30; // rax
  int v31; // r8d
  int v32; // r9d
  const WCHAR *v33; // rcx
  const WCHAR *v34; // rax
  const WCHAR *v35; // rax
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  PCSR_CAPTURE_BUFFER CaptureBuffer; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+80h] [rbp-80h] BYREF
  int v40; // [rsp+84h] [rbp-7Ch] BYREF
  int v41; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *pShimData; // [rsp+90h] [rbp-70h] BYREF
  const WCHAR *v43; // [rsp+98h] [rbp-68h] BYREF
  const WCHAR *v44; // [rsp+A0h] [rbp-60h] BYREF
  const WCHAR *v45; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE ApiMessage[52]; // [rsp+C0h] [rbp-40h] BYREF
  int v48; // [rsp+F4h] [rbp-Ch]
  PVOID v49; // [rsp+100h] [rbp+0h] BYREF
  int v50; // [rsp+108h] [rbp+8h]
  int v51; // [rsp+10Ch] [rbp+Ch]
  int v52; // [rsp+110h] [rbp+10h]
  _DWORD v53[3]; // [rsp+114h] [rbp+14h] BYREF
  unsigned __int64 v54; // [rsp+120h] [rbp+20h]
  PVOID v55; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int64 v56; // [rsp+130h] [rbp+30h]
  PVOID v57; // [rsp+138h] [rbp+38h] BYREF

  TokenHandle = 0;
  v2 = 0;
  memset_0(ApiMessage, 0, 0x3B8u);
  pShimData = (const wchar_t *)NtCurrentPeb()->pShimData;
  v3 = -1;
  if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle) >= 0 )
    goto LABEL_83;
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v4 == -1073741700 )
    v4 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v4 >= 0 )
  {
LABEL_83:
    if ( !(unsigned int)TestShutdownPrivilege(TokenHandle) )
    {
      NtClose(TokenHandle);
      v5 = 5;
LABEL_79:
      RtlSetLastWin32Error(v5);
      return v2;
    }
    NtClose(TokenHandle);
    if ( !a1 || ((*(_DWORD *)a1 - 32) & 0xFFFFFFEF) != 0 )
    {
      v5 = 87;
      goto LABEL_79;
    }
    Heap = (const unsigned __int16 **)RtlAllocateHeap(pUserHeap, 0, 0x20u);
    v7 = Heap;
    if ( !Heap )
      return v2;
    *(_OWORD *)Heap = *(_OWORD *)a1;
    *((_OWORD *)Heap + 1) = *(_OWORD *)(a1 + 16);
    if ( *(_DWORD *)a1 == 48 )
    {
      *(_DWORD *)Heap = 32;
      v8 = *(const unsigned __int16 **)(a1 + 40);
      v9 = *(const unsigned __int16 **)(a1 + 32);
    }
    else
    {
      v8 = 0;
      v9 = 0;
    }
    LODWORD(v56) = 0;
    v10 = 3;
    LODWORD(v54) = 0;
    v11 = 1138;
    v53[0] = 0;
    v12 = Heap[3];
    if ( v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      if ( v13 )
      {
        v10 = 4;
        LODWORD(v56) = v13 + 1;
        v11 = 2 * v13 + 1140;
      }
    }
    CaptureBuffer = CsrAllocateCaptureBuffer(v10, v11 + 7 * v10);
    if ( !CaptureBuffer )
    {
LABEL_26:
      RtlFreeHeap(pUserHeap, 0, v7);
      return v2;
    }
    v14 = (unsigned __int16 *)RtlAllocateHeap(pUserHeap, 0, 0x412u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_23;
    if ( v9 )
    {
      StringCchCopyW(v14, 0x209u, v9);
    }
    else if ( !(unsigned int)GetCurrentProcessName(v14, 521) )
    {
LABEL_23:
      v16 = CaptureBuffer;
      goto LABEL_24;
    }
    if ( v8 )
    {
      StringCchCatW(v15, 0x209u, L" (");
      StringCchCatW(v15, 0x209u, v8);
      StringCchCatW(v15, 0x209u, L")");
    }
    v17 = -1;
    do
      ++v17;
    while ( v15[v17] );
    v16 = CaptureBuffer;
    v53[0] = v17 + 1;
    CsrAllocateMessagePointer(CaptureBuffer, (2 * (v17 + 1) + 7) & 0xFFFFFFF8, (PVOID *)&v53[1]);
    StringCchCopyW(*(unsigned __int16 **)&v53[1], v53[0], v15);
    if ( (*((_DWORD *)v7 + 1) & 0x4008) != 0 )
    {
      v18 = 707;
    }
    else if ( (*((_DWORD *)v7 + 1) & 0x1002) != 0 )
    {
      v18 = 708;
    }
    else
    {
      v18 = 706;
      if ( (*((_DWORD *)v7 + 1) & 0x801) == 0 )
        v18 = 709;
    }
    LoadStringBaseExW(hmodUser, v18, v15, 32, 0);
    v19 = -1;
    do
      ++v19;
    while ( v15[v19] );
    LODWORD(v54) = v19 + 1;
    CsrAllocateMessagePointer(v16, (2 * (v19 + 1) + 7) & 0xFFFFFFF8, &v55);
    StringCchCopyW((unsigned __int16 *)v55, (unsigned int)v54, v15);
    CsrAllocateMessagePointer(v16, 0x20u, &v49);
    v20 = v49;
    *(_OWORD *)v49 = *(_OWORD *)v7;
    v20[1] = *((_OWORD *)v7 + 1);
    v21 = v7[3];
    if ( v21 )
    {
      v22 = -1;
      do
        ++v22;
      while ( v21[v22] );
      if ( !v22 )
        *((_QWORD *)v49 + 3) = 0;
    }
    v23 = v7[3];
    if ( v23 )
    {
      do
        ++v3;
      while ( v23[v3] );
      if ( v3 )
      {
        CsrAllocateMessagePointer(v16, (2 * v56 + 7) & 0xFFFFFFF8, &v57);
        StringCchCopyW((unsigned __int16 *)v57, (unsigned int)v56, v7[3]);
      }
    }
    if ( *((_DWORD *)v7 + 3) != 1 )
    {
      if ( *((_DWORD *)v7 + 3) == 2 )
      {
        v24 = -2147482573;
        goto LABEL_58;
      }
      if ( *((_DWORD *)v7 + 3) != 3 )
      {
        if ( *((_DWORD *)v7 + 3) != 4 )
        {
LABEL_24:
          CsrFreeCaptureBuffer(v16);
          if ( v15 )
            RtlFreeHeap(pUserHeap, 0, v15);
          goto LABEL_26;
        }
        v24 = -2147482572;
LABEL_58:
        v50 = v24;
        v25 = 0;
        v51 = *((_DWORD *)v7 + 3);
        v52 = *((_DWORD *)v7 + 4);
        CsrClientCallServer(ApiMessage, v16, (CSR_API_NUMBER)0x30405, 0x40u);
        LOBYTE(v2) = v48 >= 0;
        if ( ((v24 + 2147482575) & 0xFFFFFFF9) == 0 && v24 != -2147482569 )
        {
          v26 = OpenEventW(2u, 0, L"Global\\USORebootCancel");
          v27 = v26;
          if ( v26 )
          {
            SetEvent(v26);
            CloseHandle(v27);
          }
        }
        if ( v9 )
        {
          v28 = wcsrchr(v9, 0x5Cu);
          if ( v28 )
            v9 = v28 + 1;
        }
        if ( pShimData )
        {
          v29 = pShimData + 1438;
          v30 = wcsrchr(pShimData + 1438, 0x5Cu);
          if ( v30 )
            v25 = v30 + 1;
          else
            v25 = v29;
        }
        if ( (unsigned int)dword_1800C87A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C87A8, 0x400000000000LL) )
        {
          v46 = 0x1000000;
          v33 = &pszFormat;
          v34 = &pszFormat;
          if ( v25 )
            v34 = v25;
          v43 = v34;
          v35 = &pszFormat;
          if ( (_DWORD)v54 )
            v35 = (const WCHAR *)v55;
          v44 = v35;
          if ( v9 )
            v33 = v9;
          v39 = v52;
          v40 = v51;
          v41 = v50;
          LODWORD(pShimData) = *((_DWORD *)v7 + 2);
          LODWORD(CaptureBuffer) = *((_DWORD *)v7 + 1);
          v45 = v33;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v33,
            (unsigned int)word_1800AE4CA,
            v31,
            v32,
            (__int64)&v46,
            (__int64)&CaptureBuffer,
            (__int64)&pShimData,
            (__int64)&v41,
            (__int64)&v40,
            (__int64)&v39,
            (__int64)&v45,
            (__int64)&v44,
            (__int64)&v43);
        }
        goto LABEL_24;
      }
      if ( *((_DWORD *)v7 + 4) )
      {
        v24 = (*((_DWORD *)v7 + 1) & 0x40000B) != 0 ? -2147482575 : -2147482571;
        goto LABEL_58;
      }
    }
    v24 = -2147482574;
    goto LABEL_58;
  }
  SetLastNtError((unsigned int)v4);
  return v2;
}

```

## disassembly

```asm
0x1800695a0  push    rbp
0x1800695a2  push    rbx
0x1800695a3  push    rsi
0x1800695a4  push    rdi
0x1800695a5  push    r12
0x1800695a7  push    r13
0x1800695a9  push    r14
0x1800695ab  push    r15
0x1800695ad  lea     rbp, [rsp-398h]
0x1800695b5  sub     rsp, 498h
0x1800695bc  mov     rax, cs:__security_cookie
0x1800695c3  xor     rax, rsp
0x1800695c6  mov     [rbp+3D0h+var_50], rax
0x1800695cd  mov     rdi, rcx
0x1800695d0  xor     esi, esi
0x1800695d2  lea     rcx, [rbp+3D0h+ApiMessage]; void *
0x1800695d6  mov     [rsp+4D0h+TokenHandle], rsi
0x1800695db  xor     edx, edx; Val
0x1800695dd  mov     r8d, 3B8h; Size
0x1800695e3  mov     r15d, esi
0x1800695e6  call    memset_0
0x1800695eb  mov     rax, gs:60h
0x1800695f4  lea     ebx, [rsi+8]
0x1800695f7  lea     r12, [rsi-2]
0x1800695fb  xor     r8d, r8d; OpenAsSelf
0x1800695fe  lea     r9, [rsp+4D0h+TokenHandle]; TokenHandle
0x180069603  mov     edx, ebx; DesiredAccess
0x180069605  mov     rcx, [rax+2D8h]
0x18006960c  mov     [rbp+3D0h+var_440], rcx
0x180069610  mov     rcx, r12; ThreadHandle
0x180069613  call    cs:__imp_NtOpenThreadToken
0x180069619  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006961d  test    eax, eax
0x18006961f  jns     short loc_18006965B
0x180069621  lea     r9, [rsp+4D0h+TokenHandle]; TokenHandle
0x180069626  mov     r8b, 1; OpenAsSelf
0x180069629  mov     edx, ebx; DesiredAccess
0x18006962b  mov     rcx, r12; ThreadHandle
0x18006962e  call    cs:__imp_NtOpenThreadToken
0x180069634  cmp     eax, 0C000007Ch
0x180069639  jnz     short loc_18006964B
0x18006963b  lea     r8, [rsp+4D0h+TokenHandle]; TokenHandle
0x180069640  mov     edx, ebx; DesiredAccess
0x180069642  mov     rcx, r14; ProcessHandle
0x180069645  call    cs:__imp_NtOpenProcessToken
0x18006964b  test    eax, eax
0x18006964d  jns     short loc_18006965B
0x18006964f  mov     ecx, eax
0x180069651  call    SetLastNtError
0x180069656  jmp     loc_180069B3B
0x18006965b  mov     rcx, [rsp+4D0h+TokenHandle]; TokenHandle
0x180069660  call    ?TestShutdownPrivilege@@YAHPEAX@Z; TestShutdownPrivilege(void *)
0x180069665  mov     rcx, [rsp+4D0h+TokenHandle]; Handle
0x18006966a  test    eax, eax
0x18006966c  jnz     short loc_18006967E
0x18006966e  call    cs:__imp_NtClose
0x180069674  mov     ecx, 5
0x180069679  jmp     loc_180069B35
0x18006967e  call    cs:__imp_NtClose
0x180069684  test    rdi, rdi
0x180069687  jz      loc_180069B30
0x18006968d  mov     eax, [rdi]
0x18006968f  mov     r12d, 20h ; ' '
0x180069695  sub     eax, r12d
0x180069698  test    eax, 0FFFFFFEFh
0x18006969d  jnz     loc_180069B30
0x1800696a3  mov     rcx, cs:pUserHeap; HeapHandle
0x1800696aa  mov     r8d, r12d; Size
0x1800696ad  xor     edx, edx; Flags
0x1800696af  call    cs:__imp_RtlAllocateHeap
0x1800696b5  mov     rbx, rax
0x1800696b8  test    rax, rax
0x1800696bb  jz      loc_180069B3B
0x1800696c1  movups  xmm0, xmmword ptr [rdi]
0x1800696c4  movups  xmmword ptr [rax], xmm0
0x1800696c7  movups  xmm1, xmmword ptr [rdi+10h]
0x1800696cb  movups  xmmword ptr [rax+10h], xmm1
0x1800696cf  cmp     dword ptr [rdi], 30h ; '0'
0x1800696d2  jnz     short loc_1800696E3
0x1800696d4  mov     [rax], r12d
0x1800696d7  mov     r12, [rdi+28h]
0x1800696db  mov     r13, [rdi+20h]
0x1800696df  xor     edi, edi
0x1800696e1  jmp     short loc_1800696EB
0x1800696e3  xor     edi, edi
0x1800696e5  mov     r12d, edi
0x1800696e8  mov     r13d, edi
0x1800696eb  mov     dword ptr [rbp+3D0h+var_3A0], edi
0x1800696ee  mov     ecx, 3
0x1800696f3  mov     dword ptr [rbp+3D0h+var_3B0], edi
0x1800696f6  mov     r8d, 472h
0x1800696fc  mov     dword ptr [rbp+3D0h+var_3BC], edi
0x1800696ff  mov     rax, [rax+18h]
0x180069703  test    rax, rax
0x180069706  jz      short loc_18006972C
0x180069708  mov     rdx, r14
0x18006970b  inc     rdx
0x18006970e  cmp     [rax+rdx*2], di
0x180069712  jnz     short loc_18006970B
0x180069714  test    rdx, rdx
0x180069717  jz      short loc_18006972C
0x180069719  lea     eax, [rdx+1]
0x18006971c  mov     ecx, 4; ArgumentCount
0x180069721  mov     dword ptr [rbp+3D0h+var_3A0], eax
0x180069724  lea     r8d, ds:474h[rdx*2]
0x18006972c  imul    edx, ecx, 7
0x18006972f  add     edx, r8d; BufferSize
0x180069732  call    cs:__imp_CsrAllocateCaptureBuffer
0x180069738  mov     [rsp+4D0h+CaptureBuffer], rax
0x18006973d  test    rax, rax
0x180069740  jz      short loc_18006979C
0x180069742  mov     rcx, cs:pUserHeap; HeapHandle
0x180069749  xor     edx, edx; Flags
0x18006974b  mov     r8d, 412h; Size
0x180069751  call    cs:__imp_RtlAllocateHeap
0x180069757  mov     rsi, rax
0x18006975a  test    rax, rax
0x18006975d  jz      short loc_180069777
0x18006975f  mov     edi, 209h
0x180069764  mov     rcx, rax; unsigned __int16 *
0x180069767  test    r13, r13
0x18006976a  jnz     short loc_1800697B3
0x18006976c  mov     edx, edi; int
0x18006976e  call    ?GetCurrentProcessName@@YAHPEAGH@Z; GetCurrentProcessName(ushort *,int)
0x180069773  test    eax, eax
0x180069775  jnz     short loc_1800697BE
0x180069777  mov     r12, [rsp+4D0h+CaptureBuffer]
0x18006977c  mov     rcx, r12; CaptureBuffer
0x18006977f  call    cs:__imp_CsrFreeCaptureBuffer
0x180069785  test    rsi, rsi
0x180069788  jz      short loc_18006979C
0x18006978a  mov     rcx, cs:pUserHeap; HeapHandle
0x180069791  mov     r8, rsi; P
0x180069794  xor     edx, edx; Flags
0x180069796  call    cs:__imp_RtlFreeHeap
0x18006979c  mov     rcx, cs:pUserHeap; HeapHandle
0x1800697a3  mov     r8, rbx; P
0x1800697a6  xor     edx, edx; Flags
0x1800697a8  call    cs:__imp_RtlFreeHeap
0x1800697ae  jmp     loc_180069B3B
0x1800697b3  mov     r8, r13; unsigned __int16 *
0x1800697b6  mov     rdx, rdi; unsigned __int64
0x1800697b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800697be  test    r12, r12
0x1800697c1  jz      short loc_1800697F5
0x1800697c3  lea     r8, asc_1800AB98C; " ("
0x1800697ca  mov     rdx, rdi; unsigned __int64
0x1800697cd  mov     rcx, rsi; unsigned __int16 *
0x1800697d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800697d5  mov     r8, r12; unsigned __int16 *
0x1800697d8  mov     rdx, rdi; unsigned __int64
0x1800697db  mov     rcx, rsi; unsigned __int16 *
0x1800697de  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800697e3  lea     r8, asc_1800AB994; ")"
0x1800697ea  mov     rdx, rdi; unsigned __int64
0x1800697ed  mov     rcx, rsi; unsigned __int16 *
0x1800697f0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800697f5  mov     rax, r14
0x1800697f8  xor     edi, edi
0x1800697fa  inc     rax
0x1800697fd  cmp     [rsi+rax*2], di
0x180069801  jnz     short loc_1800697FA
0x180069803  mov     r12, [rsp+4D0h+CaptureBuffer]
0x180069808  lea     r8, [rbp+3D0h+var_3BC+4]; CapturedData
0x18006980c  inc     eax
0x18006980e  mov     rcx, r12; CaptureBuffer
0x180069811  mov     dword ptr [rbp+3D0h+var_3BC], eax
0x180069814  lea     edx, ds:7[rax*2]
0x18006981b  and     edx, 0FFFFFFF8h; MessageLength
0x18006981e  call    cs:__imp_CsrAllocateMessagePointer
0x180069824  mov     edx, dword ptr [rbp+3D0h+var_3BC]; unsigned __int64
0x180069827  mov     r8, rsi; unsigned __int16 *
0x18006982a  mov     rcx, qword ptr [rbp+3D0h+var_3BC+4]; unsigned __int16 *
0x18006982e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180069833  test    dword ptr [rbx+4], 4008h
0x18006983a  jz      short loc_180069843
0x18006983c  mov     edx, 2C3h
0x180069841  jmp     short loc_180069866
0x180069843  test    dword ptr [rbx+4], 1002h
0x18006984a  jz      short loc_180069853
0x18006984c  mov     edx, 2C4h
0x180069851  jmp     short loc_180069866
0x180069853  test    dword ptr [rbx+4], 801h
0x18006985a  mov     edx, 2C2h
0x18006985f  jnz     short loc_180069866
0x180069861  mov     edx, 2C5h
0x180069866  mov     rcx, cs:hmodUser
0x18006986d  mov     r9d, 20h ; ' '
0x180069873  mov     r8, rsi
0x180069876  mov     word ptr [rsp+4D0h+var_4B0], di
0x18006987b  call    cs:__imp_LoadStringBaseExW
0x180069881  mov     rax, r14
0x180069884  inc     rax
0x180069887  cmp     [rsi+rax*2], di
0x18006988b  jnz     short loc_180069884
0x18006988d  inc     eax
0x18006988f  lea     r8, [rbp+3D0h+var_3A8]; CapturedData
0x180069893  mov     rcx, r12; CaptureBuffer
0x180069896  mov     dword ptr [rbp+3D0h+var_3B0], eax
0x180069899  lea     edx, ds:7[rax*2]
0x1800698a0  and     edx, 0FFFFFFF8h; MessageLength
0x1800698a3  call    cs:__imp_CsrAllocateMessagePointer
0x1800698a9  mov     edx, dword ptr [rbp+3D0h+var_3B0]; unsigned __int64
0x1800698ac  mov     r8, rsi; unsigned __int16 *
0x1800698af  mov     rcx, [rbp+3D0h+var_3A8]; unsigned __int16 *
0x1800698b3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800698b8  lea     r8, [rbp+3D0h+var_3D0]; CapturedData
0x1800698bc  mov     edx, 20h ; ' '; MessageLength
0x1800698c1  mov     rcx, r12; CaptureBuffer
0x1800698c4  call    cs:__imp_CsrAllocateMessagePointer
0x1800698ca  mov     rax, [rbp+3D0h+var_3D0]
0x1800698ce  movups  xmm0, xmmword ptr [rbx]
0x1800698d1  movups  xmmword ptr [rax], xmm0
0x1800698d4  movups  xmm1, xmmword ptr [rbx+10h]
0x1800698d8  movups  xmmword ptr [rax+10h], xmm1
0x1800698dc  mov     rcx, [rbx+18h]
0x1800698e0  test    rcx, rcx
0x1800698e3  jz      short loc_1800698FE
0x1800698e5  mov     rax, r14
0x1800698e8  inc     rax
0x1800698eb  cmp     [rcx+rax*2], di
0x1800698ef  jnz     short loc_1800698E8
0x1800698f1  test    rax, rax
0x1800698f4  jnz     short loc_1800698FE
0x1800698f6  mov     rax, [rbp+3D0h+var_3D0]
0x1800698fa  mov     [rax+18h], rdi
0x1800698fe  mov     rax, [rbx+18h]
0x180069902  test    rax, rax
0x180069905  jz      short loc_180069940
0x180069907  inc     r14
0x18006990a  cmp     [rax+r14*2], di
0x18006990f  jnz     short loc_180069907
0x180069911  test    r14, r14
0x180069914  jz      short loc_180069940
0x180069916  mov     eax, dword ptr [rbp+3D0h+var_3A0]
0x180069919  lea     r8, [rbp+3D0h+var_398]; CapturedData
0x18006991d  mov     rcx, r12; CaptureBuffer
0x180069920  lea     edx, ds:7[rax*2]
0x180069927  and     edx, 0FFFFFFF8h; MessageLength
0x18006992a  call    cs:__imp_CsrAllocateMessagePointer
0x180069930  mov     edx, dword ptr [rbp+3D0h+var_3A0]; unsigned __int64
0x180069933  mov     r8, [rbx+18h]; unsigned __int16 *
0x180069937  mov     rcx, [rbp+3D0h+var_398]; unsigned __int16 *
0x18006993b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180069940  mov     ecx, [rbx+0Ch]
0x180069943  sub     ecx, 1
0x180069946  jz      short loc_180069985
0x180069948  sub     ecx, 1
0x18006994b  jz      short loc_18006997E
0x18006994d  sub     ecx, 1
0x180069950  jz      short loc_180069962
0x180069952  cmp     ecx, 1
0x180069955  jnz     loc_18006977C
0x18006995b  mov     edi, 80000434h
0x180069960  jmp     short loc_18006998A
0x180069962  cmp     [rbx+10h], edi
0x180069965  jz      short loc_180069985
0x180069967  mov     eax, [rbx+4]
0x18006996a  and     eax, 40000Bh
0x18006996f  neg     eax
0x180069971  sbb     edi, edi
0x180069973  and     edi, 0FFFFFFFCh
0x180069976  add     edi, 80000435h
0x18006997c  jmp     short loc_18006998A
0x18006997e  mov     edi, 80000433h
0x180069983  jmp     short loc_18006998A
0x180069985  mov     edi, 80000432h
0x18006998a  mov     [rbp+3D0h+var_3C8], edi
0x18006998d  lea     rcx, [rbp+3D0h+ApiMessage]; ApiMessage
0x180069991  mov     eax, [rbx+0Ch]
0x180069994  xor     r14d, r14d
0x180069997  mov     [rbp+3D0h+var_3C4], eax
0x18006999a  mov     r8d, 30405h; ApiNumber
0x1800699a0  mov     eax, [rbx+10h]
0x1800699a3  mov     rdx, r12; CaptureBuffer
0x1800699a6  mov     [rbp+3D0h+var_3C0], eax
0x1800699a9  lea     r9d, [r14+40h]; DataLength
0x1800699ad  call    cs:__imp_CsrClientCallServer
0x1800699b3  xor     eax, eax
0x1800699b5  cmp     [rbp+3D0h+var_3DC], eax
0x1800699b8  lea     eax, [rdi+7FFFFBCFh]
0x1800699be  setnl   r15b
0x1800699c2  test    eax, 0FFFFFFF9h
0x1800699c7  jnz     short loc_1800699FD
0x1800699c9  cmp     edi, 80000437h
0x1800699cf  jz      short loc_1800699FD
0x1800699d1  xor     edx, edx; bInheritHandle
0x1800699d3  lea     r8, Name; "Global\\USORebootCancel"
0x1800699da  lea     ecx, [rdx+2]; dwDesiredAccess
0x1800699dd  call    cs:__imp_OpenEventW
0x1800699e3  mov     rdi, rax
0x1800699e6  test    rax, rax
0x1800699e9  jz      short loc_1800699FD
0x1800699eb  mov     rcx, rax; hEvent
0x1800699ee  call    cs:__imp_SetEvent
0x1800699f4  mov     rcx, rdi; hObject
0x1800699f7  call    cs:__imp_CloseHandle
0x1800699fd  xor     edi, edi
0x1800699ff  test    r13, r13
0x180069a02  jz      short loc_180069A19
  ... truncated ...
```
