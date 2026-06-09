# KeyManagement::CreateTrustlet(_GUID,_PS_TRUSTLET_TKSESSION_ID *,_TRUSTLET_MAILBOX_KEY *,ushort const *,ushort const *,void * *)

- ea: `0x14027ae68`
- end: `0x14027b219`
- name: `?CreateTrustlet@KeyManagement@@YAJU_GUID@@PEAU_PS_TRUSTLET_TKSESSION_ID@@PEAU_TRUSTLET_MAILBOX_KEY@@PEBG3PEAPEAX@Z`
- size: `945`
- prototype: `__int64 __fastcall(KeyManagement *__hidden this, struct _GUID *, struct _PS_TRUSTLET_TKSESSION_ID *, struct _TRUSTLET_MAILBOX_KEY *, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x14027abb0`

## callees

- `0x14011ea40`
- `0x14011f6fc`
- `0x14027ae68`

## import_xrefs

- `ntdll!NtClose` at `0x14027b173`
- `ntdll!NtClose` at `0x14027b183`
- `ntdll!NtClose` at `0x14027b173`
- `ntdll!NtClose` at `0x14027b183`
- `ntdll!RtlInitUnicodeString` at `0x14027af1d`
- `ntdll!RtlInitUnicodeString` at `0x14027af1d`
- `ntdll!RtlCreateProcessParametersEx` at `0x14027b05e`
- `ntdll!RtlCreateProcessParametersEx` at `0x14027b05e`
- `ntdll!RtlNtStatusToDosError` at `0x14027b1bc`
- `ntdll!RtlNtStatusToDosError` at `0x14027b1ce`
- `ntdll!RtlNtStatusToDosError` at `0x14027b1de`
- `ntdll!RtlNtStatusToDosError` at `0x14027b1bc`
- `ntdll!RtlNtStatusToDosError` at `0x14027b1ce`
- `ntdll!RtlNtStatusToDosError` at `0x14027b1de`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14027af9c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14027af9c`
- `ntdll!RtlFreeHeap` at `0x14027b1aa`
- `ntdll!RtlFreeHeap` at `0x14027b1aa`
- `ntdll!NtCreateUserProcess` at `0x14027b14f`
- `ntdll!NtCreateUserProcess` at `0x14027b14f`

## pseudocode

```c
__int64 __fastcall KeyManagement::CreateTrustlet(
        KeyManagement *this,
        struct _GUID *a2,
        struct _PS_TRUSTLET_TKSESSION_ID *a3,
        struct _TRUSTLET_MAILBOX_KEY *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  unsigned int v10; // edi
  NTSTATUS v11; // ebx
  __int128 v12; // xmm0
  struct _GUID v13; // xmm1
  __int128 v14; // xmm0
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rax
  __int16 v17; // dx
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // r14
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+80h] [rbp-80h]
  _BYTE v23[4]; // [rsp+84h] [rbp-7Ch] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-78h] BYREF
  HANDLE v25; // [rsp+90h] [rbp-70h] BYREF
  char v26; // [rsp+98h] [rbp-68h] BYREF
  __int128 v27; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v28[14]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v29; // [rsp+170h] [rbp+70h] BYREF
  int v30; // [rsp+178h] [rbp+78h] BYREF
  __int128 v31; // [rsp+180h] [rbp+80h]
  int v32; // [rsp+190h] [rbp+90h]
  __int128 v33; // [rsp+198h] [rbp+98h]
  int v34; // [rsp+1A8h] [rbp+A8h]
  __int128 v35; // [rsp+1B0h] [rbp+B0h]
  struct _GUID v36; // [rsp+1C0h] [rbp+C0h]
  _QWORD v37[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v38; // [rsp+1E0h] [rbp+E0h]

  memset_0(v28, 0, 0x68u);
  v29 = 0;
  memset_0(&v30, 0, 0x58u);
  memset_0(v37, 0, 0x58u);
  v20 = 0;
  v10 = 0;
  v27 = 0;
  DestinationString = 0;
  if ( a6 )
    *(_QWORD *)a6 = 0;
  memset_0(v23, 0, 0x64u);
  v22 = 104;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( !a2 )
  {
    v11 = -1073741811;
    goto LABEL_18;
  }
  v12 = *(_OWORD *)a3;
  v13 = a2[1];
  v30 = TrustletType_MailboxKey;
  v31 = v12;
  v32 = TrustletType_CollaborationId;
  v33 = *(_OWORD *)this;
  v29 = 2;
  v14 = (__int128)*a2;
  v34 = TrustletType_TkSessionId;
  v36 = v13;
  v35 = v14;
  v11 = RtlDosPathNameToNtPathName_U_WithStatus(a4, &DestinationString, 0, 0);
  if ( v11 >= 0 )
  {
    v27 = 0;
    if ( a5 )
    {
      v15 = 0x7FFF;
      v16 = a5;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v15;
      }
      while ( v15 );
      v11 = v15 == 0 ? 0xC000000D : 0;
      if ( !v15 )
        goto LABEL_18;
      v17 = 2 * v15;
      *((_QWORD *)&v27 + 1) = a5;
      LOWORD(v27) = -2 - v17;
      WORD1(v27) = -v17;
    }
    ProcessParameters = NtCurrentPeb()->ProcessParameters;
    v11 = RtlCreateProcessParametersEx(&v20, &DestinationString, 0, 0, &v27, 0, 0, 0, 0, 0, 1);
    if ( v11 >= 0 )
    {
      *(_DWORD *)(v20 + 1032) = ProcessParameters[1].Flags;
      memset_0(v37, 0, 0x58u);
      v37[0] = 88;
      v28[3] = &v26;
      v28[6] = DestinationString.Length;
      v28[7] = DestinationString.Buffer;
      v28[11] = &v29;
      v38 = 4;
      v28[1] = 65539;
      v28[2] = 16;
      v28[4] = 0;
      v28[5] = 131077;
      v28[8] = 0;
      v28[9] = 131090;
      v28[10] = 96;
      v28[12] = 0;
      v28[0] = 104;
      v11 = NtCreateUserProcess(&Handle, &v25, 0x2000000, 0x2000000, 0, 0, 256, 0, v20, v37, v28);
      if ( v11 >= 0 )
      {
        if ( a6 )
          *(_QWORD *)a6 = Handle;
        else
          NtClose(Handle);
        NtClose(v25);
      }
    }
  }
LABEL_18:
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  if ( v11 < 0 )
  {
    if ( (int)RtlNtStatusToDosError(v11) > 0 )
      return (unsigned __int16)RtlNtStatusToDosError(v11) | 0x80070000;
    else
      return RtlNtStatusToDosError(v11);
  }
  return v10;
}

```

## disassembly

```asm
0x14027ae68  push    rbp
0x14027ae6a  push    rbx
0x14027ae6b  push    rsi
0x14027ae6c  push    rdi
0x14027ae6d  push    r12
0x14027ae6f  push    r13
0x14027ae71  push    r14
0x14027ae73  push    r15
0x14027ae75  lea     rbp, [rsp-148h]
0x14027ae7d  sub     rsp, 248h
0x14027ae84  mov     rax, cs:__security_cookie
0x14027ae8b  xor     rax, rsp
0x14027ae8e  mov     [rbp+180h+var_50], rax
0x14027ae95  mov     rsi, [rbp+180h+arg_28]
0x14027ae9c  mov     rbx, rdx
0x14027ae9f  xor     edx, edx; Val
0x14027aea1  mov     r14, r8
0x14027aea4  mov     r15, rcx
0x14027aea7  mov     r12, r9
0x14027aeaa  lea     rcx, [rbp+180h+var_180]; void *
0x14027aeae  lea     r8d, [rdx+68h]; Size
0x14027aeb2  call    memset_0
0x14027aeb7  xor     r13d, r13d
0x14027aeba  lea     rcx, [rbp+180h+var_108]; void *
0x14027aebe  xor     edx, edx; Val
0x14027aec0  mov     [rbp+180h+var_110], r13
0x14027aec4  lea     edi, [r13+58h]
0x14027aec8  mov     r8d, edi; Size
0x14027aecb  call    memset_0
0x14027aed0  mov     r8d, edi; Size
0x14027aed3  lea     rcx, [rbp+180h+var_B0]; void *
0x14027aeda  xor     edx, edx; Val
0x14027aedc  call    memset_0
0x14027aee1  mov     [rsp+280h+var_220], r13
0x14027aee6  xorps   xmm0, xmm0
0x14027aee9  xorps   xmm1, xmm1
0x14027aeec  mov     edi, r13d
0x14027aeef  movups  [rbp+180h+var_190], xmm0
0x14027aef3  movups  xmmword ptr [rsp+280h+DestinationString.Length], xmm1
0x14027aef8  test    rsi, rsi
0x14027aefb  jz      short loc_14027AF00
0x14027aefd  mov     [rsi], r13
0x14027af00  xor     edx, edx; Val
0x14027af02  lea     rcx, [rbp+180h+var_1FC]; void *
0x14027af06  lea     r8d, [rdx+64h]; Size
0x14027af0a  call    memset_0
0x14027af0f  xor     edx, edx; SourceString
0x14027af11  mov     [rbp+180h+var_200], 68h ; 'h'
0x14027af18  lea     rcx, [rsp+280h+DestinationString]; DestinationString
0x14027af1d  call    cs:__imp_RtlInitUnicodeString
0x14027af24  nop     dword ptr [rax+rax+00h]
0x14027af29  test    rbx, rbx
0x14027af2c  jnz     short loc_14027AF38
0x14027af2e  mov     ebx, 0C000000Dh
0x14027af33  jmp     loc_14027B18F
0x14027af38  movups  xmm0, xmmword ptr [r14]
0x14027af3c  mov     eax, cs:TrustletType_MailboxKey
0x14027af42  lea     rdx, [rsp+280h+DestinationString]
0x14027af47  movups  xmm1, xmmword ptr [rbx+10h]
0x14027af4b  mov     [rbp+180h+var_108], eax
0x14027af4e  xor     r9d, r9d
0x14027af51  mov     eax, cs:TrustletType_CollaborationId
0x14027af57  xor     r8d, r8d
0x14027af5a  movdqu  [rbp+180h+var_100], xmm0
0x14027af62  mov     rcx, r12
0x14027af65  mov     [rbp+180h+var_F0], eax
0x14027af6b  movaps  xmm0, xmmword ptr [r15]
0x14027af6f  mov     eax, cs:TrustletType_TkSessionId
0x14027af75  movdqu  [rbp+180h+var_E8], xmm0
0x14027af7d  mov     [rbp+180h+var_110], 2
0x14027af85  movups  xmm0, xmmword ptr [rbx]
0x14027af88  mov     [rbp+180h+var_D8], eax
0x14027af8e  movaps  [rbp+180h+var_C0], xmm1
0x14027af95  movaps  [rbp+180h+var_D0], xmm0
0x14027af9c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14027afa3  nop     dword ptr [rax+rax+00h]
0x14027afa8  mov     ebx, eax
0x14027afaa  test    eax, eax
0x14027afac  js      loc_14027B18F
0x14027afb2  mov     r8, [rbp+180h+arg_20]
0x14027afb9  xorps   xmm0, xmm0
0x14027afbc  movups  [rbp+180h+var_190], xmm0
0x14027afc0  test    r8, r8
0x14027afc3  jz      short loc_14027B017
0x14027afc5  mov     edx, 7FFFh
0x14027afca  mov     rax, r8
0x14027afcd  mov     r9d, 2
0x14027afd3  cmp     [rax], r13w
0x14027afd7  jz      short loc_14027AFE2
0x14027afd9  add     rax, r9
0x14027afdc  sub     rdx, 1
0x14027afe0  jnz     short loc_14027AFD3
0x14027afe2  mov     rax, rdx
0x14027afe5  mov     ebx, 0C000000Dh
0x14027afea  neg     rax
0x14027afed  sbb     ecx, ecx
0x14027afef  not     ecx
0x14027aff1  and     ebx, ecx
0x14027aff3  test    rdx, rdx
0x14027aff6  jz      loc_14027B18F
0x14027affc  add     dx, dx
0x14027afff  mov     qword ptr [rbp+180h+var_190+8], r8
0x14027b003  mov     eax, 0FFFEh
0x14027b008  sub     ax, dx
0x14027b00b  mov     word ptr [rbp+180h+var_190], ax
0x14027b00f  add     ax, r9w
0x14027b013  mov     word ptr [rbp+180h+var_190+2], ax
0x14027b017  mov     rax, gs:60h
0x14027b020  lea     rdx, [rsp+280h+DestinationString]
0x14027b025  mov     dword ptr [rsp+280h+var_230], 1
0x14027b02d  lea     rcx, [rsp+280h+var_220]
0x14027b032  mov     [rsp+280h+var_238], r13
0x14027b037  xor     r9d, r9d
0x14027b03a  mov     [rsp+280h+var_240], r13
0x14027b03f  xor     r8d, r8d
0x14027b042  mov     r14, [rax+20h]
0x14027b046  lea     rax, [rbp+180h+var_190]
0x14027b04a  mov     [rsp+280h+var_248], r13
0x14027b04f  mov     [rsp+280h+var_250], r13
0x14027b054  mov     [rsp+280h+var_258], r13
0x14027b059  mov     [rsp+280h+var_260], rax
0x14027b05e  call    cs:__imp_RtlCreateProcessParametersEx
0x14027b065  nop     dword ptr [rax+rax+00h]
0x14027b06a  mov     ebx, eax
0x14027b06c  test    eax, eax
0x14027b06e  js      loc_14027B18F
0x14027b074  mov     ecx, [r14+408h]
0x14027b07b  mov     ebx, 58h ; 'X'
0x14027b080  mov     rax, [rsp+280h+var_220]
0x14027b085  mov     r8d, ebx; Size
0x14027b088  xor     edx, edx; Val
0x14027b08a  mov     [rax+408h], ecx
0x14027b090  lea     rcx, [rbp+180h+var_B0]; void *
0x14027b097  call    memset_0
0x14027b09c  lea     rax, [rbp+180h+var_1E8]
0x14027b0a0  mov     [rbp+180h+var_B0], rbx
0x14027b0a7  mov     [rbp+180h+var_168], rax
0x14027b0ab  lea     rdx, [rbp+180h+var_1F0]
0x14027b0af  movzx   eax, [rsp+280h+DestinationString.Length]
0x14027b0b4  lea     rcx, [rbp+180h+Handle]
0x14027b0b8  mov     [rbp+180h+var_150], rax
0x14027b0bc  mov     r8d, 2000000h
0x14027b0c2  mov     rax, [rsp+280h+DestinationString.Buffer]
0x14027b0c7  mov     r9d, r8d
0x14027b0ca  mov     [rbp+180h+var_148], rax
0x14027b0ce  lea     rax, [rbp+180h+var_110]
0x14027b0d2  mov     [rbp+180h+var_128], rax
0x14027b0d6  lea     rax, [rbp+180h+var_180]
0x14027b0da  mov     [rsp+280h+var_230], rax
0x14027b0df  lea     rax, [rbp+180h+var_B0]
0x14027b0e6  mov     [rsp+280h+var_238], rax
0x14027b0eb  mov     rax, [rsp+280h+var_220]
0x14027b0f0  mov     [rsp+280h+var_240], rax
0x14027b0f5  mov     dword ptr [rsp+280h+var_248], r13d
0x14027b0fa  mov     dword ptr [rsp+280h+var_250], 100h
0x14027b102  mov     [rsp+280h+var_258], r13
0x14027b107  mov     [rsp+280h+var_260], r13
0x14027b10c  mov     [rbp+180h+var_A0], 4
0x14027b113  mov     [rbp+180h+var_178], 10003h
0x14027b11b  mov     [rbp+180h+var_170], 10h
0x14027b123  mov     [rbp+180h+var_160], r13
0x14027b127  mov     [rbp+180h+var_158], 20005h
0x14027b12f  mov     [rbp+180h+var_140], r13
0x14027b133  mov     [rbp+180h+var_138], 20012h
0x14027b13b  mov     [rbp+180h+var_130], 60h ; '`'
0x14027b143  mov     [rbp+180h+var_120], r13
0x14027b147  mov     [rbp+180h+var_180], 68h ; 'h'
0x14027b14f  call    cs:__imp_NtCreateUserProcess
0x14027b156  nop     dword ptr [rax+rax+00h]
0x14027b15b  mov     ebx, eax
0x14027b15d  test    eax, eax
0x14027b15f  js      short loc_14027B18F
0x14027b161  test    rsi, rsi
0x14027b164  jz      short loc_14027B16F
0x14027b166  mov     rax, [rbp+180h+Handle]
0x14027b16a  mov     [rsi], rax
0x14027b16d  jmp     short loc_14027B17F
0x14027b16f  mov     rcx, [rbp+180h+Handle]; Handle
0x14027b173  call    cs:__imp_NtClose
0x14027b17a  nop     dword ptr [rax+rax+00h]
0x14027b17f  mov     rcx, [rbp+180h+var_1F0]; Handle
0x14027b183  call    cs:__imp_NtClose
0x14027b18a  nop     dword ptr [rax+rax+00h]
0x14027b18f  cmp     [rsp+280h+DestinationString.Buffer], r13
0x14027b194  jz      short loc_14027B1B6
0x14027b196  mov     rcx, gs:60h
0x14027b19f  xor     edx, edx; Flags
0x14027b1a1  mov     r8, [rsp+280h+DestinationString.Buffer]; P
0x14027b1a6  mov     rcx, [rcx+30h]; HeapHandle
0x14027b1aa  call    cs:__imp_RtlFreeHeap
0x14027b1b1  nop     dword ptr [rax+rax+00h]
0x14027b1b6  test    ebx, ebx
0x14027b1b8  jns     short loc_14027B1F3
0x14027b1ba  mov     ecx, ebx; Status
0x14027b1bc  call    cs:__imp_RtlNtStatusToDosError
0x14027b1c3  nop     dword ptr [rax+rax+00h]
0x14027b1c8  mov     ecx, ebx; Status
0x14027b1ca  test    eax, eax
0x14027b1cc  jg      short loc_14027B1DE
0x14027b1ce  call    cs:__imp_RtlNtStatusToDosError
0x14027b1d5  nop     dword ptr [rax+rax+00h]
0x14027b1da  mov     edi, eax
0x14027b1dc  jmp     short loc_14027B1F3
0x14027b1de  call    cs:__imp_RtlNtStatusToDosError
0x14027b1e5  nop     dword ptr [rax+rax+00h]
0x14027b1ea  movzx   edi, ax
0x14027b1ed  or      edi, 80070000h
0x14027b1f3  mov     eax, edi
0x14027b1f5  mov     rcx, [rbp+180h+var_50]
0x14027b1fc  xor     rcx, rsp; StackCookie
0x14027b1ff  call    __security_check_cookie
0x14027b204  add     rsp, 248h
0x14027b20b  pop     r15
0x14027b20d  pop     r14
0x14027b20f  pop     r13
0x14027b211  pop     r12
0x14027b213  pop     rdi
0x14027b214  pop     rsi
0x14027b215  pop     rbx
0x14027b216  pop     rbp
0x14027b217  retn
```
