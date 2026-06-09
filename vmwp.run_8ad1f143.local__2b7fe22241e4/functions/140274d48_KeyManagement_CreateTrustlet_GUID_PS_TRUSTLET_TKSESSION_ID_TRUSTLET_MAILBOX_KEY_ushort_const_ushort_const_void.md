# KeyManagement::CreateTrustlet(_GUID,_PS_TRUSTLET_TKSESSION_ID *,_TRUSTLET_MAILBOX_KEY *,ushort const *,ushort const *,void * *)

- ea: `0x140274d48`
- end: `0x1402750f9`
- name: `?CreateTrustlet@KeyManagement@@YAJU_GUID@@PEAU_PS_TRUSTLET_TKSESSION_ID@@PEAU_TRUSTLET_MAILBOX_KEY@@PEBG3PEAPEAX@Z`
- size: `945`
- prototype: `__int64 __fastcall(KeyManagement *__hidden this, struct _GUID *, struct _PS_TRUSTLET_TKSESSION_ID *, struct _TRUSTLET_MAILBOX_KEY *, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x140274a90`

## callees

- `0x140132960`
- `0x14013361c`
- `0x140274d48`

## import_xrefs

- `ntdll!NtClose` at `0x140275053`
- `ntdll!NtClose` at `0x140275063`
- `ntdll!NtClose` at `0x140275053`
- `ntdll!NtClose` at `0x140275063`
- `ntdll!RtlInitUnicodeString` at `0x140274dfd`
- `ntdll!RtlInitUnicodeString` at `0x140274dfd`
- `ntdll!RtlCreateProcessParametersEx` at `0x140274f3e`
- `ntdll!RtlCreateProcessParametersEx` at `0x140274f3e`
- `ntdll!RtlNtStatusToDosError` at `0x14027509c`
- `ntdll!RtlNtStatusToDosError` at `0x1402750ae`
- `ntdll!RtlNtStatusToDosError` at `0x1402750be`
- `ntdll!RtlNtStatusToDosError` at `0x14027509c`
- `ntdll!RtlNtStatusToDosError` at `0x1402750ae`
- `ntdll!RtlNtStatusToDosError` at `0x1402750be`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140274e7c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140274e7c`
- `ntdll!RtlFreeHeap` at `0x14027508a`
- `ntdll!RtlFreeHeap` at `0x14027508a`
- `ntdll!NtCreateUserProcess` at `0x14027502f`
- `ntdll!NtCreateUserProcess` at `0x14027502f`

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
0x140274d48  push    rbp
0x140274d4a  push    rbx
0x140274d4b  push    rsi
0x140274d4c  push    rdi
0x140274d4d  push    r12
0x140274d4f  push    r13
0x140274d51  push    r14
0x140274d53  push    r15
0x140274d55  lea     rbp, [rsp-148h]
0x140274d5d  sub     rsp, 248h
0x140274d64  mov     rax, cs:__security_cookie
0x140274d6b  xor     rax, rsp
0x140274d6e  mov     [rbp+180h+var_50], rax
0x140274d75  mov     rsi, [rbp+180h+arg_28]
0x140274d7c  mov     rbx, rdx
0x140274d7f  xor     edx, edx; Val
0x140274d81  mov     r14, r8
0x140274d84  mov     r15, rcx
0x140274d87  mov     r12, r9
0x140274d8a  lea     rcx, [rbp+180h+var_180]; void *
0x140274d8e  lea     r8d, [rdx+68h]; Size
0x140274d92  call    memset_0
0x140274d97  xor     r13d, r13d
0x140274d9a  lea     rcx, [rbp+180h+var_108]; void *
0x140274d9e  xor     edx, edx; Val
0x140274da0  mov     [rbp+180h+var_110], r13
0x140274da4  lea     edi, [r13+58h]
0x140274da8  mov     r8d, edi; Size
0x140274dab  call    memset_0
0x140274db0  mov     r8d, edi; Size
0x140274db3  lea     rcx, [rbp+180h+var_B0]; void *
0x140274dba  xor     edx, edx; Val
0x140274dbc  call    memset_0
0x140274dc1  mov     [rsp+280h+var_220], r13
0x140274dc6  xorps   xmm0, xmm0
0x140274dc9  xorps   xmm1, xmm1
0x140274dcc  mov     edi, r13d
0x140274dcf  movups  [rbp+180h+var_190], xmm0
0x140274dd3  movups  xmmword ptr [rsp+280h+DestinationString.Length], xmm1
0x140274dd8  test    rsi, rsi
0x140274ddb  jz      short loc_140274DE0
0x140274ddd  mov     [rsi], r13
0x140274de0  xor     edx, edx; Val
0x140274de2  lea     rcx, [rbp+180h+var_1FC]; void *
0x140274de6  lea     r8d, [rdx+64h]; Size
0x140274dea  call    memset_0
0x140274def  xor     edx, edx; SourceString
0x140274df1  mov     [rbp+180h+var_200], 68h ; 'h'
0x140274df8  lea     rcx, [rsp+280h+DestinationString]; DestinationString
0x140274dfd  call    cs:__imp_RtlInitUnicodeString
0x140274e04  nop     dword ptr [rax+rax+00h]
0x140274e09  test    rbx, rbx
0x140274e0c  jnz     short loc_140274E18
0x140274e0e  mov     ebx, 0C000000Dh
0x140274e13  jmp     loc_14027506F
0x140274e18  movups  xmm0, xmmword ptr [r14]
0x140274e1c  mov     eax, cs:TrustletType_MailboxKey
0x140274e22  lea     rdx, [rsp+280h+DestinationString]
0x140274e27  movups  xmm1, xmmword ptr [rbx+10h]
0x140274e2b  mov     [rbp+180h+var_108], eax
0x140274e2e  xor     r9d, r9d
0x140274e31  mov     eax, cs:TrustletType_CollaborationId
0x140274e37  xor     r8d, r8d
0x140274e3a  movdqu  [rbp+180h+var_100], xmm0
0x140274e42  mov     rcx, r12
0x140274e45  mov     [rbp+180h+var_F0], eax
0x140274e4b  movaps  xmm0, xmmword ptr [r15]
0x140274e4f  mov     eax, cs:TrustletType_TkSessionId
0x140274e55  movdqu  [rbp+180h+var_E8], xmm0
0x140274e5d  mov     [rbp+180h+var_110], 2
0x140274e65  movups  xmm0, xmmword ptr [rbx]
0x140274e68  mov     [rbp+180h+var_D8], eax
0x140274e6e  movaps  [rbp+180h+var_C0], xmm1
0x140274e75  movaps  [rbp+180h+var_D0], xmm0
0x140274e7c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140274e83  nop     dword ptr [rax+rax+00h]
0x140274e88  mov     ebx, eax
0x140274e8a  test    eax, eax
0x140274e8c  js      loc_14027506F
0x140274e92  mov     r8, [rbp+180h+arg_20]
0x140274e99  xorps   xmm0, xmm0
0x140274e9c  movups  [rbp+180h+var_190], xmm0
0x140274ea0  test    r8, r8
0x140274ea3  jz      short loc_140274EF7
0x140274ea5  mov     edx, 7FFFh
0x140274eaa  mov     rax, r8
0x140274ead  mov     r9d, 2
0x140274eb3  cmp     [rax], r13w
0x140274eb7  jz      short loc_140274EC2
0x140274eb9  add     rax, r9
0x140274ebc  sub     rdx, 1
0x140274ec0  jnz     short loc_140274EB3
0x140274ec2  mov     rax, rdx
0x140274ec5  mov     ebx, 0C000000Dh
0x140274eca  neg     rax
0x140274ecd  sbb     ecx, ecx
0x140274ecf  not     ecx
0x140274ed1  and     ebx, ecx
0x140274ed3  test    rdx, rdx
0x140274ed6  jz      loc_14027506F
0x140274edc  add     dx, dx
0x140274edf  mov     qword ptr [rbp+180h+var_190+8], r8
0x140274ee3  mov     eax, 0FFFEh
0x140274ee8  sub     ax, dx
0x140274eeb  mov     word ptr [rbp+180h+var_190], ax
0x140274eef  add     ax, r9w
0x140274ef3  mov     word ptr [rbp+180h+var_190+2], ax
0x140274ef7  mov     rax, gs:60h
0x140274f00  lea     rdx, [rsp+280h+DestinationString]
0x140274f05  mov     dword ptr [rsp+280h+var_230], 1
0x140274f0d  lea     rcx, [rsp+280h+var_220]
0x140274f12  mov     [rsp+280h+var_238], r13
0x140274f17  xor     r9d, r9d
0x140274f1a  mov     [rsp+280h+var_240], r13
0x140274f1f  xor     r8d, r8d
0x140274f22  mov     r14, [rax+20h]
0x140274f26  lea     rax, [rbp+180h+var_190]
0x140274f2a  mov     [rsp+280h+var_248], r13
0x140274f2f  mov     [rsp+280h+var_250], r13
0x140274f34  mov     [rsp+280h+var_258], r13
0x140274f39  mov     [rsp+280h+var_260], rax
0x140274f3e  call    cs:__imp_RtlCreateProcessParametersEx
0x140274f45  nop     dword ptr [rax+rax+00h]
0x140274f4a  mov     ebx, eax
0x140274f4c  test    eax, eax
0x140274f4e  js      loc_14027506F
0x140274f54  mov     ecx, [r14+408h]
0x140274f5b  mov     ebx, 58h ; 'X'
0x140274f60  mov     rax, [rsp+280h+var_220]
0x140274f65  mov     r8d, ebx; Size
0x140274f68  xor     edx, edx; Val
0x140274f6a  mov     [rax+408h], ecx
0x140274f70  lea     rcx, [rbp+180h+var_B0]; void *
0x140274f77  call    memset_0
0x140274f7c  lea     rax, [rbp+180h+var_1E8]
0x140274f80  mov     [rbp+180h+var_B0], rbx
0x140274f87  mov     [rbp+180h+var_168], rax
0x140274f8b  lea     rdx, [rbp+180h+var_1F0]
0x140274f8f  movzx   eax, [rsp+280h+DestinationString.Length]
0x140274f94  lea     rcx, [rbp+180h+Handle]
0x140274f98  mov     [rbp+180h+var_150], rax
0x140274f9c  mov     r8d, 2000000h
0x140274fa2  mov     rax, [rsp+280h+DestinationString.Buffer]
0x140274fa7  mov     r9d, r8d
0x140274faa  mov     [rbp+180h+var_148], rax
0x140274fae  lea     rax, [rbp+180h+var_110]
0x140274fb2  mov     [rbp+180h+var_128], rax
0x140274fb6  lea     rax, [rbp+180h+var_180]
0x140274fba  mov     [rsp+280h+var_230], rax
0x140274fbf  lea     rax, [rbp+180h+var_B0]
0x140274fc6  mov     [rsp+280h+var_238], rax
0x140274fcb  mov     rax, [rsp+280h+var_220]
0x140274fd0  mov     [rsp+280h+var_240], rax
0x140274fd5  mov     dword ptr [rsp+280h+var_248], r13d
0x140274fda  mov     dword ptr [rsp+280h+var_250], 100h
0x140274fe2  mov     [rsp+280h+var_258], r13
0x140274fe7  mov     [rsp+280h+var_260], r13
0x140274fec  mov     [rbp+180h+var_A0], 4
0x140274ff3  mov     [rbp+180h+var_178], 10003h
0x140274ffb  mov     [rbp+180h+var_170], 10h
0x140275003  mov     [rbp+180h+var_160], r13
0x140275007  mov     [rbp+180h+var_158], 20005h
0x14027500f  mov     [rbp+180h+var_140], r13
0x140275013  mov     [rbp+180h+var_138], 20012h
0x14027501b  mov     [rbp+180h+var_130], 60h ; '`'
0x140275023  mov     [rbp+180h+var_120], r13
0x140275027  mov     [rbp+180h+var_180], 68h ; 'h'
0x14027502f  call    cs:__imp_NtCreateUserProcess
0x140275036  nop     dword ptr [rax+rax+00h]
0x14027503b  mov     ebx, eax
0x14027503d  test    eax, eax
0x14027503f  js      short loc_14027506F
0x140275041  test    rsi, rsi
0x140275044  jz      short loc_14027504F
0x140275046  mov     rax, [rbp+180h+Handle]
0x14027504a  mov     [rsi], rax
0x14027504d  jmp     short loc_14027505F
0x14027504f  mov     rcx, [rbp+180h+Handle]; Handle
0x140275053  call    cs:__imp_NtClose
0x14027505a  nop     dword ptr [rax+rax+00h]
0x14027505f  mov     rcx, [rbp+180h+var_1F0]; Handle
0x140275063  call    cs:__imp_NtClose
0x14027506a  nop     dword ptr [rax+rax+00h]
0x14027506f  cmp     [rsp+280h+DestinationString.Buffer], r13
0x140275074  jz      short loc_140275096
0x140275076  mov     rcx, gs:60h
0x14027507f  xor     edx, edx; Flags
0x140275081  mov     r8, [rsp+280h+DestinationString.Buffer]; P
0x140275086  mov     rcx, [rcx+30h]; HeapHandle
0x14027508a  call    cs:__imp_RtlFreeHeap
0x140275091  nop     dword ptr [rax+rax+00h]
0x140275096  test    ebx, ebx
0x140275098  jns     short loc_1402750D3
0x14027509a  mov     ecx, ebx; Status
0x14027509c  call    cs:__imp_RtlNtStatusToDosError
0x1402750a3  nop     dword ptr [rax+rax+00h]
0x1402750a8  mov     ecx, ebx; Status
0x1402750aa  test    eax, eax
0x1402750ac  jg      short loc_1402750BE
0x1402750ae  call    cs:__imp_RtlNtStatusToDosError
0x1402750b5  nop     dword ptr [rax+rax+00h]
0x1402750ba  mov     edi, eax
0x1402750bc  jmp     short loc_1402750D3
0x1402750be  call    cs:__imp_RtlNtStatusToDosError
0x1402750c5  nop     dword ptr [rax+rax+00h]
0x1402750ca  movzx   edi, ax
0x1402750cd  or      edi, 80070000h
0x1402750d3  mov     eax, edi
0x1402750d5  mov     rcx, [rbp+180h+var_50]
0x1402750dc  xor     rcx, rsp; StackCookie
0x1402750df  call    __security_check_cookie
0x1402750e4  add     rsp, 248h
0x1402750eb  pop     r15
0x1402750ed  pop     r14
0x1402750ef  pop     r13
0x1402750f1  pop     r12
0x1402750f3  pop     rdi
0x1402750f4  pop     rsi
0x1402750f5  pop     rbx
0x1402750f6  pop     rbp
0x1402750f7  retn
```
