# ClientCreateOnDemandContext(WCM_ONDEMAND_HANDLE_CONTEXT * *)

- ea: `0x18000c7c0`
- end: `0x18000c8d0`
- name: `?ClientCreateOnDemandContext@@YAKPEAPEAUWCM_ONDEMAND_HANDLE_CONTEXT@@@Z`
- size: `272`
- prototype: `unsigned int __fastcall(struct WCM_ONDEMAND_HANDLE_CONTEXT **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012670`
- `0x180012b10`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180004d10`
- `0x180005070`
- `0x18000c7c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c852`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000c87c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000c87c`

## string_xrefs

- `0x18000c7f0`: `ClientCreateOnDemandContext`
- `0x18000c8a7`: `ClientCreateOnDemandContext`

## pseudocode

```c
__int64 __fastcall ClientCreateOnDemandContext(struct WCM_ONDEMAND_HANDLE_CONTEXT **a1)
{
  WcmPolicyManager *v2; // rcx
  DWORD LastError; // ebx
  __int64 v4; // rax
  struct WCM_ONDEMAND_HANDLE_CONTEXT *v5; // rdi

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      86,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "ClientCreateOnDemandContext");
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v4 = WcmAlloc(0x38u);
    v5 = (struct WCM_ONDEMAND_HANDLE_CONTEXT *)v4;
    if ( v4 )
    {
      *(_OWORD *)v4 = 0;
      LastError = 0;
      *(_OWORD *)(v4 + 16) = 0;
      *(_OWORD *)(v4 + 32) = 0;
      *(_QWORD *)(v4 + 48) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v4 + 16));
      *a1 = v5;
    }
    else
    {
      LastError = GetLastError();
    }
    goto LABEL_13;
  }
  LastError = 87;
  if ( v2 == (WcmPolicyManager *)&WPP_GLOBAL_Control )
    return LastError;
  if ( *((_BYTE *)v2 + 25) && (*((_BYTE *)v2 + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v2 + 2), 87, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids);
LABEL_13:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 5u && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v2 + 2),
      88,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"ClientCreateOnDemandContext",
      LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000c7c0  push    rbx
0x18000c7c2  push    rsi
0x18000c7c3  push    rdi
0x18000c7c4  push    r14
0x18000c7c6  sub     rsp, 38h
0x18000c7ca  mov     rsi, rcx
0x18000c7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7d4  lea     r14, WPP_GLOBAL_Control
0x18000c7db  cmp     rcx, r14
0x18000c7de  jz      short loc_18000C80F
0x18000c7e0  cmp     byte ptr [rcx+19h], 5
0x18000c7e4  jb      short loc_18000C80F
0x18000c7e6  test    byte ptr [rcx+1Ch], 1
0x18000c7ea  jz      short loc_18000C80F
0x18000c7ec  mov     rcx, [rcx+10h]
0x18000c7f0  lea     r9, aClientcreateon; "ClientCreateOnDemandContext"
0x18000c7f7  mov     edx, 56h ; 'V'
0x18000c7fc  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18000c803  call    WPP_SF_s
0x18000c808  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c80f  test    rsi, rsi
0x18000c812  jnz     short loc_18000C840
0x18000c814  lea     ebx, [rsi+57h]
0x18000c817  cmp     rcx, r14
0x18000c81a  jz      loc_18000C8C3
0x18000c820  cmp     byte ptr [rcx+19h], 1
0x18000c824  jb      short loc_18000C892
0x18000c826  test    byte ptr [rcx+1Ch], 1
0x18000c82a  jz      short loc_18000C892
0x18000c82c  mov     rcx, [rcx+10h]
0x18000c830  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18000c837  mov     edx, ebx
0x18000c839  call    WPP_SF_
0x18000c83e  jmp     short loc_18000C88B
0x18000c840  mov     ecx, 38h ; '8'; dwBytes
0x18000c845  call    WcmAlloc
0x18000c84a  mov     rdi, rax
0x18000c84d  test    rax, rax
0x18000c850  jnz     short loc_18000C862
0x18000c852  call    cs:__imp_GetLastError
0x18000c859  nop     dword ptr [rax+rax+00h]
0x18000c85e  mov     ebx, eax
0x18000c860  jmp     short loc_18000C88B
0x18000c862  xorps   xmm0, xmm0
0x18000c865  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000c869  movups  xmmword ptr [rdi], xmm0
0x18000c86c  xor     eax, eax
0x18000c86e  xor     ebx, ebx
0x18000c870  movups  xmmword ptr [rdi+10h], xmm0
0x18000c874  movups  xmmword ptr [rdi+20h], xmm0
0x18000c878  mov     [rdi+30h], rax
0x18000c87c  call    cs:__imp_InitializeCriticalSection
0x18000c883  nop     dword ptr [rax+rax+00h]
0x18000c888  mov     [rsi], rdi
0x18000c88b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c892  cmp     rcx, r14
0x18000c895  jz      short loc_18000C8C3
0x18000c897  cmp     byte ptr [rcx+19h], 5
0x18000c89b  jb      short loc_18000C8C3
0x18000c89d  test    byte ptr [rcx+1Ch], 1
0x18000c8a1  jz      short loc_18000C8C3
0x18000c8a3  mov     rcx, [rcx+10h]
0x18000c8a7  lea     r9, aClientcreateon; "ClientCreateOnDemandContext"
0x18000c8ae  mov     edx, 58h ; 'X'
0x18000c8b3  mov     [rsp+58h+var_38], ebx
0x18000c8b7  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18000c8be  call    WPP_SF_sL
0x18000c8c3  mov     eax, ebx
0x18000c8c5  add     rsp, 38h
0x18000c8c9  pop     r14
0x18000c8cb  pop     rdi
0x18000c8cc  pop     rsi
0x18000c8cd  pop     rbx
0x18000c8ce  retn
```
