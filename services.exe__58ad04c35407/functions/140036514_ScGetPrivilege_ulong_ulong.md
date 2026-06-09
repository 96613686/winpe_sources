# ScGetPrivilege(ulong,ulong *)

- ea: `0x140036514`
- end: `0x1400367b8`
- name: `?ScGetPrivilege@@YAKKPEAK@Z`
- size: `676`
- prototype: `unsigned int __fastcall(unsigned int, unsigned int *)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000ac68`
- `0x140015df0`
- `0x140033b5c`
- `0x1400379d8`
- `0x140064d34`
- `0x140065130`
- `0x140065b00`
- `0x14007341c`
- `0x1400735a0`
- `0x140076eb0`
- `0x14007be28`

## callees

- `0x140004c58`
- `0x140036514`
- `0x1400575b0`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x140036657`
- `ntdll!NtDuplicateToken` at `0x140036657`
- `ntdll!NtAdjustPrivilegesToken` at `0x1400366d7`
- `ntdll!NtAdjustPrivilegesToken` at `0x1400366d7`
- `ntdll!NtSetInformationThread` at `0x140036750`
- `ntdll!NtSetInformationThread` at `0x140036750`
- `ntdll!NtClose` at `0x140036730`
- `ntdll!NtClose` at `0x140036798`
- `ntdll!NtClose` at `0x140036730`
- `ntdll!NtClose` at `0x140036798`
- `ntdll!RtlNtStatusToDosError` at `0x1400366ae`
- `ntdll!RtlNtStatusToDosError` at `0x1400366ae`
- `ntdll!RtlFreeHeap` at `0x1400366a6`
- `ntdll!RtlFreeHeap` at `0x140036726`
- `ntdll!RtlFreeHeap` at `0x14003678e`
- `ntdll!RtlFreeHeap` at `0x1400366a6`
- `ntdll!RtlFreeHeap` at `0x140036726`
- `ntdll!RtlFreeHeap` at `0x14003678e`
- `ntdll!RtlAllocateHeap` at `0x140036576`
- `ntdll!RtlAllocateHeap` at `0x140036576`

## pseudocode

```c
ULONG __fastcall ScGetPrivilege(DWORD a1, unsigned int *a2)
{
  struct _TOKEN_PRIVILEGES *Heap; // rax
  struct _TOKEN_PRIVILEGES *v5; // rbx
  DWORD v7; // r8d
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // edi
  PRPC_ASYNC_STATE v11; // rcx
  __int64 v12; // rdx
  HANDLE TokenHandle; // [rsp+30h] [rbp-29h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-21h] BYREF
  __int64 v15; // [rsp+40h] [rbp-19h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-11h] BYREF
  __int64 v17; // [rsp+78h] [rbp+1Fh] BYREF
  int v18; // [rsp+80h] [rbp+27h]

  TokenHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v17 = 0;
  v18 = 0;
  ReturnLength = 0;
  Heap = (struct _TOKEN_PRIVILEGES *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 12LL * a1 + 16);
  v5 = Heap;
  if ( Heap )
  {
    v7 = 0;
    Heap->PrivilegeCount = a1;
    if ( a1 )
    {
      v8 = 0;
      do
      {
        v9 = v8;
        LODWORD(v15) = a2[v8];
        ++v7;
        ++v8;
        v15 = (int)v15;
        Heap->Privileges[v9].Luid = (LUID)(int)v15;
        Heap->Privileges[v9].Attributes = 2;
      }
      while ( v7 < a1 );
    }
    ObjectAttributes.SecurityQualityOfService = &v17;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    ObjectAttributes.SecurityDescriptor = 0;
    v17 = 0x20000000CLL;
    LOWORD(v18) = 0;
    v10 = NtDuplicateToken(g_hProcessToken, 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, &TokenHandle);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 49, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, (unsigned int)v10);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      return RtlNtStatusToDosError(v10);
    }
    v10 = NtAdjustPrivilegesToken(TokenHandle, 0, v5, 0, 0, &ReturnLength);
    if ( v10 >= 0 )
    {
      v10 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
      if ( v10 >= 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
        NtClose(TokenHandle);
        return 0;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_20;
      v12 = 51;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_20;
      v12 = 50;
    }
    WPP_SF_d(v11->StubInfo, v12, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, (unsigned int)v10);
LABEL_20:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    NtClose(TokenHandle);
    return RtlNtStatusToDosError(v10);
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 48, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, 8);
  return 8;
}

```

## disassembly

```asm
0x140036514  push    rbp
0x140036516  push    rbx
0x140036517  push    rsi
0x140036518  push    rdi
0x140036519  lea     rbp, [rsp-3Fh]
0x14003651e  sub     rsp, 98h
0x140036525  mov     rax, cs:__security_cookie
0x14003652c  xor     rax, rsp
0x14003652f  mov     [rbp+57h+var_28], rax
0x140036533  xorps   xmm0, xmm0
0x140036536  mov     edi, ecx
0x140036538  xor     eax, eax
0x14003653a  mov     [rbp+57h+TokenHandle], 0
0x140036542  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140036546  mov     [rbp+57h+var_38], rax
0x14003654a  mov     rsi, rdx
0x14003654d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140036551  mov     [rbp+57h+var_30], eax
0x140036554  lea     r8, [rdi+rdi*2]
0x140036558  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003655c  mov     [rbp+57h+ReturnLength], eax
0x14003655f  lea     r8, ds:10h[r8*4]; Size
0x140036567  mov     rcx, gs:60h
0x140036570  xor     edx, edx; Flags
0x140036572  mov     rcx, [rcx+30h]; HeapHandle
0x140036576  call    cs:__imp_RtlAllocateHeap
0x14003657c  mov     rbx, rax
0x14003657f  test    rax, rax
0x140036582  jnz     short loc_1400365BE
0x140036584  mov     rcx, cs:WPP_GLOBAL_Control
0x14003658b  lea     rax, WPP_GLOBAL_Control
0x140036592  cmp     rcx, rax
0x140036595  jz      short loc_1400365B4
0x140036597  test    byte ptr [rcx+1Ch], 1
0x14003659b  jz      short loc_1400365B4
0x14003659d  mov     rcx, [rcx+10h]
0x1400365a1  lea     edx, [rbx+30h]
0x1400365a4  lea     r9d, [rbx+8]
0x1400365a8  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x1400365af  call    WPP_SF_d
0x1400365b4  mov     eax, 8
0x1400365b9  jmp     loc_1400367A0
0x1400365be  xor     r8d, r8d
0x1400365c1  mov     [rax], edi
0x1400365c3  lea     r9d, [r8+2]
0x1400365c7  test    edi, edi
0x1400365c9  jz      short loc_1400365F8
0x1400365cb  xor     edx, edx
0x1400365cd  movsxd  rax, dword ptr [rsi+rdx*4]
0x1400365d1  lea     rcx, [rdx+rdx*2]
0x1400365d5  mov     dword ptr [rbp+57h+var_70], eax
0x1400365d8  inc     r8d
0x1400365db  shr     rax, 20h
0x1400365df  inc     rdx
0x1400365e2  mov     dword ptr [rbp+57h+var_70+4], eax
0x1400365e5  mov     rax, [rbp+57h+var_70]
0x1400365e9  mov     [rbx+rcx*4+4], rax
0x1400365ee  mov     [rbx+rcx*4+0Ch], r9d
0x1400365f3  cmp     r8d, edi
0x1400365f6  jb      short loc_1400365CD
0x1400365f8  mov     rcx, cs:?g_hProcessToken@@3PEAXEA; ExistingTokenHandle
0x1400365ff  lea     rax, [rbp+57h+var_38]
0x140036603  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x140036607  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14003660b  lea     rax, [rbp+57h+TokenHandle]
0x14003660f  mov     dword ptr [rbp+57h+var_38+4], r9d
0x140036613  mov     [rsp+0B0h+NewTokenHandle], rax; NewTokenHandle
0x140036618  mov     [rsp+0B0h+TokenType], r9d; TokenType
0x14003661d  xor     r9d, r9d; EffectiveOnly
0x140036620  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140036627  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14003662f  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x140036636  lea     edx, [r9+2Ch]; DesiredAccess
0x14003663a  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140036642  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x14003664a  mov     dword ptr [rbp+57h+var_38], 0Ch
0x140036651  mov     word ptr [rbp+57h+var_30], 0
0x140036657  call    cs:__imp_NtDuplicateToken
0x14003665d  mov     edi, eax
0x14003665f  test    eax, eax
0x140036661  jns     short loc_1400366B9
0x140036663  mov     rcx, cs:WPP_GLOBAL_Control
0x14003666a  lea     rax, WPP_GLOBAL_Control
0x140036671  cmp     rcx, rax
0x140036674  jz      short loc_140036694
0x140036676  test    byte ptr [rcx+1Ch], 1
0x14003667a  jz      short loc_140036694
0x14003667c  mov     rcx, [rcx+10h]
0x140036680  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140036687  mov     edx, 31h ; '1'
0x14003668c  mov     r9d, edi
0x14003668f  call    WPP_SF_d
0x140036694  mov     rcx, gs:60h
0x14003669d  mov     r8, rbx; P
0x1400366a0  xor     edx, edx; Flags
0x1400366a2  mov     rcx, [rcx+30h]; HeapHandle
0x1400366a6  call    cs:__imp_RtlFreeHeap
0x1400366ac  mov     ecx, edi; Status
0x1400366ae  call    cs:__imp_RtlNtStatusToDosError
0x1400366b4  jmp     loc_1400367A0
0x1400366b9  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400366bd  lea     rax, [rbp+57h+ReturnLength]
0x1400366c1  mov     [rsp+0B0h+NewTokenHandle], rax; ReturnLength
0x1400366c6  xor     r9d, r9d; BufferLength
0x1400366c9  mov     r8, rbx; NewState
0x1400366cc  mov     qword ptr [rsp+0B0h+TokenType], 0; PreviousState
0x1400366d5  xor     edx, edx; DisableAllPrivileges
0x1400366d7  call    cs:__imp_NtAdjustPrivilegesToken
0x1400366dd  mov     edi, eax
0x1400366df  test    eax, eax
0x1400366e1  jns     short loc_14003673B
0x1400366e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400366ea  lea     rax, WPP_GLOBAL_Control
0x1400366f1  cmp     rcx, rax
0x1400366f4  jz      short loc_140036714
0x1400366f6  test    byte ptr [rcx+1Ch], 1
0x1400366fa  jz      short loc_140036714
0x1400366fc  mov     edx, 32h ; '2'
0x140036701  mov     rcx, [rcx+10h]
0x140036705  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x14003670c  mov     r9d, edi
0x14003670f  call    WPP_SF_d
0x140036714  mov     rcx, gs:60h
0x14003671d  mov     r8, rbx; P
0x140036720  xor     edx, edx; Flags
0x140036722  mov     rcx, [rcx+30h]; HeapHandle
0x140036726  call    cs:__imp_RtlFreeHeap
0x14003672c  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x140036730  call    cs:__imp_NtClose
0x140036736  jmp     loc_1400366AC
0x14003673b  mov     r9d, 8; ThreadInformationLength
0x140036741  lea     r8, [rbp+57h+TokenHandle]; ThreadInformation
0x140036745  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14003674c  lea     edx, [r9-3]; ThreadInformationClass
0x140036750  call    cs:__imp_NtSetInformationThread
0x140036756  mov     edi, eax
0x140036758  test    eax, eax
0x14003675a  jns     short loc_14003677C
0x14003675c  mov     rcx, cs:WPP_GLOBAL_Control
0x140036763  lea     rax, WPP_GLOBAL_Control
0x14003676a  cmp     rcx, rax
0x14003676d  jz      short loc_140036714
0x14003676f  test    byte ptr [rcx+1Ch], 1
0x140036773  jz      short loc_140036714
0x140036775  mov     edx, 33h ; '3'
0x14003677a  jmp     short loc_140036701
0x14003677c  mov     rcx, gs:60h
0x140036785  mov     r8, rbx; P
0x140036788  xor     edx, edx; Flags
0x14003678a  mov     rcx, [rcx+30h]; HeapHandle
0x14003678e  call    cs:__imp_RtlFreeHeap
0x140036794  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x140036798  call    cs:__imp_NtClose
0x14003679e  xor     eax, eax
0x1400367a0  mov     rcx, [rbp+57h+var_28]
0x1400367a4  xor     rcx, rsp; StackCookie
0x1400367a7  call    __security_check_cookie
0x1400367ac  add     rsp, 98h
0x1400367b3  pop     rdi
0x1400367b4  pop     rsi
0x1400367b5  pop     rbx
0x1400367b6  pop     rbp
0x1400367b7  retn
```
