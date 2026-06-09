# ScAdjustTokenDefaultDacl(void *,void * *,ulong)

- ea: `0x1400355b8`
- end: `0x14003587c`
- name: `?ScAdjustTokenDefaultDacl@@YAKPEAXPEAPEAXK@Z`
- size: `708`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, void **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140063928`

## callees

- `0x140004c58`
- `0x1400355b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003566d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400356c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003576a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400357bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003566d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400356c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003576a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400357bc`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1400357b2`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1400357b2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1400356b8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140035707`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x14003575c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1400356b8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140035707`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x14003575c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140035663`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140035663`
- `ntdll!RtlLengthSid` at `0x1400355da`
- `ntdll!RtlLengthSid` at `0x1400355ed`
- `ntdll!RtlLengthSid` at `0x1400355fc`
- `ntdll!RtlLengthSid` at `0x1400355da`
- `ntdll!RtlLengthSid` at `0x1400355ed`
- `ntdll!RtlLengthSid` at `0x1400355fc`
- `ntdll!RtlFreeHeap` at `0x140035867`
- `ntdll!RtlFreeHeap` at `0x140035867`
- `ntdll!RtlAllocateHeap` at `0x14003561e`
- `ntdll!RtlAllocateHeap` at `0x14003561e`

## pseudocode

```c
__int64 __fastcall ScAdjustTokenDefaultDacl(HANDLE TokenHandle, void **a2, unsigned int a3)
{
  ULONG v6; // edi
  ULONG v7; // edi
  unsigned int v8; // ebx
  DWORD v9; // edi
  struct _ACL *Heap; // rax
  struct _ACL *v11; // rsi
  PRPC_ASYNC_STATE v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  DWORD LastError; // eax
  __int64 i; // rdi
  struct _ACL *TokenInformation; // [rsp+78h] [rbp+20h] BYREF

  TokenInformation = 0;
  v6 = a3 * (RtlLengthSid(*a2) + 12);
  v7 = RtlLengthSid(OwnerSid) + v6;
  v8 = 8;
  v9 = RtlLengthSid(LocalSystemSid) + 32 + v7;
  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v9);
  v11 = Heap;
  if ( Heap )
  {
    if ( InitializeAcl(Heap, v9, 2u) )
    {
      if ( AddAccessAllowedAce(v11, 2u, 0x10000000u, LocalSystemSid) )
      {
        if ( AddAccessAllowedAce(v11, 2u, 0x20000u, OwnerSid) )
        {
          for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
          {
            if ( !AddAccessAllowedAce(v11, 2u, 0x10000000u, a2[i]) )
            {
              LastError = GetLastError();
              v8 = LastError;
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                v13 = 107;
                goto LABEL_9;
              }
              goto LABEL_38;
            }
          }
          TokenInformation = v11;
          if ( SetTokenInformation(TokenHandle, TokenDefaultDacl, &TokenInformation, 8u) )
          {
            v12 = WPP_GLOBAL_Control;
            v8 = 0;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
            {
              v13 = 110;
              v14 = a3;
              goto LABEL_37;
            }
          }
          else
          {
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError == 1344 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 108, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, 1344);
              }
              v8 = 0;
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                v13 = 109;
                goto LABEL_9;
              }
            }
          }
          goto LABEL_38;
        }
        LastError = GetLastError();
        v8 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_38;
        }
        v13 = 106;
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_38;
        }
        v13 = 105;
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_38;
      v13 = 104;
    }
LABEL_9:
    v14 = LastError;
    goto LABEL_37;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v13 = 103;
    v14 = 8;
LABEL_37:
    WPP_SF_d(v12->StubInfo, v13, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, v14);
  }
LABEL_38:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  return v8;
}

```

## disassembly

```asm
0x1400355b8  push    rbx
0x1400355ba  push    rbp
0x1400355bb  push    rsi
0x1400355bc  push    rdi
0x1400355bd  push    r14
0x1400355bf  push    r15
0x1400355c1  sub     rsp, 28h
0x1400355c5  mov     r15, rcx
0x1400355c8  mov     [rsp+58h+TokenInformation], 0
0x1400355d1  mov     rcx, [rdx]; Sid
0x1400355d4  mov     ebp, r8d
0x1400355d7  mov     r14, rdx
0x1400355da  call    cs:__imp_RtlLengthSid
0x1400355e0  mov     rcx, cs:OwnerSid; Sid
0x1400355e7  lea     edi, [rax+0Ch]
0x1400355ea  imul    edi, ebp
0x1400355ed  call    cs:__imp_RtlLengthSid
0x1400355f3  mov     rcx, cs:LocalSystemSid; Sid
0x1400355fa  add     edi, eax
0x1400355fc  call    cs:__imp_RtlLengthSid
0x140035602  mov     rcx, gs:60h
0x14003560b  mov     ebx, 8
0x140035610  add     eax, 20h ; ' '
0x140035613  mov     edx, ebx; Flags
0x140035615  add     edi, eax
0x140035617  mov     r8d, edi; Size
0x14003561a  mov     rcx, [rcx+30h]; HeapHandle
0x14003561e  call    cs:__imp_RtlAllocateHeap
0x140035624  mov     rsi, rax
0x140035627  test    rax, rax
0x14003562a  jnz     short loc_140035658
0x14003562c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035633  lea     rdx, WPP_GLOBAL_Control
0x14003563a  cmp     rcx, rdx
0x14003563d  jz      loc_140035855
0x140035643  test    byte ptr [rcx+1Ch], 1
0x140035647  jz      loc_140035855
0x14003564d  lea     edx, [rbx+5Fh]
0x140035650  mov     r9d, ebx
0x140035653  jmp     loc_140035845
0x140035658  mov     r8d, 2; dwAclRevision
0x14003565e  mov     edx, edi; nAclLength
0x140035660  mov     rcx, rsi; pAcl
0x140035663  call    cs:__imp_InitializeAcl
0x140035669  test    eax, eax
0x14003566b  jnz     short loc_1400356A3
0x14003566d  call    cs:__imp_GetLastError
0x140035673  mov     ebx, eax
0x140035675  mov     rcx, cs:WPP_GLOBAL_Control
0x14003567c  lea     rdx, WPP_GLOBAL_Control
0x140035683  cmp     rcx, rdx
0x140035686  jz      loc_140035855
0x14003568c  test    byte ptr [rcx+1Ch], 1
0x140035690  jz      loc_140035855
0x140035696  mov     edx, 68h ; 'h'
0x14003569b  mov     r9d, eax
0x14003569e  jmp     loc_140035845
0x1400356a3  mov     r9, cs:LocalSystemSid; pSid
0x1400356aa  mov     edx, 2; dwAceRevision
0x1400356af  mov     r8d, 10000000h; AccessMask
0x1400356b5  mov     rcx, rsi; pAcl
0x1400356b8  call    cs:__imp_AddAccessAllowedAce
0x1400356be  test    eax, eax
0x1400356c0  jnz     short loc_1400356F2
0x1400356c2  call    cs:__imp_GetLastError
0x1400356c8  mov     ebx, eax
0x1400356ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400356d1  lea     rdx, WPP_GLOBAL_Control
0x1400356d8  cmp     rcx, rdx
0x1400356db  jz      loc_140035855
0x1400356e1  test    byte ptr [rcx+1Ch], 1
0x1400356e5  jz      loc_140035855
0x1400356eb  mov     edx, 69h ; 'i'
0x1400356f0  jmp     short loc_14003569B
0x1400356f2  mov     r9, cs:OwnerSid; pSid
0x1400356f9  mov     edx, 2; dwAceRevision
0x1400356fe  mov     r8d, 20000h; AccessMask
0x140035704  mov     rcx, rsi; pAcl
0x140035707  call    cs:__imp_AddAccessAllowedAce
0x14003570d  test    eax, eax
0x14003570f  jnz     short loc_140035744
0x140035711  call    cs:__imp_GetLastError
0x140035717  mov     ebx, eax
0x140035719  mov     rcx, cs:WPP_GLOBAL_Control
0x140035720  lea     rdx, WPP_GLOBAL_Control
0x140035727  cmp     rcx, rdx
0x14003572a  jz      loc_140035855
0x140035730  test    byte ptr [rcx+1Ch], 1
0x140035734  jz      loc_140035855
0x14003573a  mov     edx, 6Ah ; 'j'
0x14003573f  jmp     loc_14003569B
0x140035744  xor     edi, edi
0x140035746  cmp     edi, ebp
0x140035748  jnb     short loc_14003579D
0x14003574a  mov     r9, [r14+rdi*8]; pSid
0x14003574e  mov     edx, 2; dwAceRevision
0x140035753  mov     r8d, 10000000h; AccessMask
0x140035759  mov     rcx, rsi; pAcl
0x14003575c  call    cs:__imp_AddAccessAllowedAce
0x140035762  test    eax, eax
0x140035764  jz      short loc_14003576A
0x140035766  inc     edi
0x140035768  jmp     short loc_140035746
0x14003576a  call    cs:__imp_GetLastError
0x140035770  mov     ebx, eax
0x140035772  mov     rcx, cs:WPP_GLOBAL_Control
0x140035779  lea     rdx, WPP_GLOBAL_Control
0x140035780  cmp     rcx, rdx
0x140035783  jz      loc_140035855
0x140035789  test    byte ptr [rcx+1Ch], 1
0x14003578d  jz      loc_140035855
0x140035793  mov     edx, 6Bh ; 'k'
0x140035798  jmp     loc_14003569B
0x14003579d  mov     r9d, ebx; TokenInformationLength
0x1400357a0  mov     [rsp+58h+TokenInformation], rsi
0x1400357a5  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x1400357aa  mov     edx, 6; TokenInformationClass
0x1400357af  mov     rcx, r15; TokenHandle
0x1400357b2  call    cs:__imp_SetTokenInformation
0x1400357b8  test    eax, eax
0x1400357ba  jnz     short loc_140035824
0x1400357bc  call    cs:__imp_GetLastError
0x1400357c2  mov     r9d, 540h
0x1400357c8  mov     ebx, eax
0x1400357ca  cmp     eax, r9d
0x1400357cd  jnz     short loc_140035801
0x1400357cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400357d6  lea     rdx, WPP_GLOBAL_Control
0x1400357dd  cmp     rcx, rdx
0x1400357e0  jz      short loc_1400357FD
0x1400357e2  test    byte ptr [rcx+1Ch], 2
0x1400357e6  jz      short loc_1400357FD
0x1400357e8  mov     rcx, [rcx+10h]
0x1400357ec  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x1400357f3  mov     edx, 6Ch ; 'l'
0x1400357f8  call    WPP_SF_d
0x1400357fd  xor     ebx, ebx
0x1400357ff  jmp     short loc_140035855
0x140035801  mov     rcx, cs:WPP_GLOBAL_Control
0x140035808  lea     rdx, WPP_GLOBAL_Control
0x14003580f  cmp     rcx, rdx
0x140035812  jz      short loc_140035855
0x140035814  test    byte ptr [rcx+1Ch], 1
0x140035818  jz      short loc_140035855
0x14003581a  mov     edx, 6Dh ; 'm'
0x14003581f  jmp     loc_14003569B
0x140035824  mov     rcx, cs:WPP_GLOBAL_Control
0x14003582b  lea     rdx, WPP_GLOBAL_Control
0x140035832  xor     ebx, ebx
0x140035834  cmp     rcx, rdx
0x140035837  jz      short loc_140035855
0x140035839  test    byte ptr [rcx+1Ch], 4
0x14003583d  jz      short loc_140035855
0x14003583f  lea     edx, [rbx+6Eh]
0x140035842  mov     r9d, ebp
0x140035845  mov     rcx, [rcx+10h]
0x140035849  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140035850  call    WPP_SF_d
0x140035855  mov     rcx, gs:60h
0x14003585e  mov     r8, rsi; P
0x140035861  xor     edx, edx; Flags
0x140035863  mov     rcx, [rcx+30h]; HeapHandle
0x140035867  call    cs:__imp_RtlFreeHeap
0x14003586d  mov     eax, ebx
0x14003586f  add     rsp, 28h
0x140035873  pop     r15
0x140035875  pop     r14
0x140035877  pop     rdi
0x140035878  pop     rsi
0x140035879  pop     rbp
0x14003587a  pop     rbx
0x14003587b  retn
```
