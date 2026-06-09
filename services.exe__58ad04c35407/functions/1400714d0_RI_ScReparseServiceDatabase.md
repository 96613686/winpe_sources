# RI_ScReparseServiceDatabase

- ea: `0x1400714d0`
- end: `0x140071792`
- name: `RI_ScReparseServiceDatabase`
- size: `706`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, loader_planting, service_task`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140017160`
- `0x14001f99c`
- `0x1400575b0`
- `0x1400702a0`
- `0x1400708c4`
- `0x1400709e0`
- `0x1400714d0`
- `0x140092060`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x14007154e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x14007154e`
- `ntdll!RtlAreAllAccessesGranted` at `0x140071633`
- `ntdll!RtlAreAllAccessesGranted` at `0x140071633`
- `ntdll!RtlFreeHeap` at `0x14007174e`
- `ntdll!RtlFreeHeap` at `0x14007176b`
- `ntdll!RtlFreeHeap` at `0x14007174e`
- `ntdll!RtlFreeHeap` at `0x14007176b`

## string_xrefs

- `0x1400714f4`: `TransactedServices`
- `0x14007150b`: `TransactedServices01`

## pseudocode

```c
__int64 __fastcall RI_ScReparseServiceDatabase(_DWORD *a1, unsigned int a2)
{
  __int64 v2; // rdi
  unsigned int v4; // ebx
  ACCESS_MASK v5; // edx
  HKEY v6; // rcx
  unsigned int v7; // r8d
  const unsigned __int16 *v8; // rbx
  unsigned int v9; // eax
  PVOID v10; // rsi
  unsigned int ReparseInfo; // eax
  PVOID v12; // rdi
  unsigned int v14; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-75h] BYREF
  PVOID v16; // [rsp+38h] [rbp-71h] BYREF
  PVOID P; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *v18[3]; // [rsp+48h] [rbp-61h]
  _DWORD RpcCallAttributes[32]; // [rsp+60h] [rbp-49h] BYREF

  v2 = a2;
  v18[0] = L"TransactedServices";
  v14 = 0;
  v15 = 0;
  v18[1] = L"TransactedServices01";
  memset(&RpcCallAttributes[2], 0, 0x70u);
  P = 0;
  v16 = 0;
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 32;
  v4 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 98, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, v4);
    return v4;
  }
  if ( RpcCallAttributes[15] != 1 )
    return 5;
  if ( (unsigned int)v2 < 2 )
  {
    if ( (unsigned int)ScIsValidScManagerHandle(a1) )
    {
      if ( !RtlAreAllAccessesGranted(a1[2], v5) )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->StubInfo, 101, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids);
        }
        return 5;
      }
      v8 = v18[v2];
      v9 = RegQueryValueWithAlloc(v6, v8, v7, (unsigned __int8 **)&v16, &v14);
      v10 = v16;
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            102,
            (unsigned int)WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
            (_DWORD)v8,
            v9);
        }
        v4 = 87;
      }
      else
      {
        ReparseInfo = ScGetReparseInfo((const unsigned __int16 *)v16, v14, (struct _SC_REPARSE_INFO **)&P, &v15);
        v12 = P;
        v4 = ReparseInfo;
        if ( ReparseInfo )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 103, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, ReparseInfo);
          }
        }
        else
        {
          v4 = ScPerformReparse((struct _SC_REPARSE_INFO *)P, v15);
        }
        if ( v12 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      }
      if ( v10 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 100, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids);
      return 6;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 99, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, (unsigned int)v2);
    return 87;
  }
  return v4;
}

```

## disassembly

```asm
0x1400714d0  mov     [rsp-8+arg_10], rbx
0x1400714d5  push    rbp
0x1400714d6  push    rsi
0x1400714d7  push    rdi
0x1400714d8  lea     rbp, [rsp-47h]
0x1400714dd  sub     rsp, 0F0h
0x1400714e4  mov     rax, cs:__security_cookie
0x1400714eb  xor     rax, rsp
0x1400714ee  mov     [rbp+57h+var_20], rax
0x1400714f2  mov     edi, edx
0x1400714f4  lea     rax, aTransactedserv; "TransactedServices"
0x1400714fb  xor     edx, edx; Val
0x1400714fd  mov     [rbp+57h+var_B8], rax
0x140071501  mov     rsi, rcx
0x140071504  mov     [rbp+57h+var_D0], 0
0x14007150b  lea     rax, aTransactedserv_0; "TransactedServices01"
0x140071512  mov     [rbp+57h+var_CC], 0
0x140071519  lea     rcx, [rbp+57h+var_98]; void *
0x14007151d  mov     [rbp+57h+var_B0], rax
0x140071521  lea     r8d, [rdx+70h]; Size
0x140071525  call    memset
0x14007152a  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x14007152e  mov     [rbp+57h+P], 0
0x140071536  xor     ecx, ecx; ClientBinding
0x140071538  mov     [rbp+57h+var_C8], 0
0x140071540  mov     [rbp+57h+RpcCallAttributes], 3
0x140071547  mov     [rbp+57h+var_9C], 20h ; ' '
0x14007154e  call    cs:__imp_RpcServerInqCallAttributesW
0x140071554  mov     ebx, eax
0x140071556  test    eax, eax
0x140071558  jz      short loc_140071598
0x14007155a  mov     rcx, cs:WPP_GLOBAL_Control
0x140071561  lea     rax, WPP_GLOBAL_Control
0x140071568  cmp     rcx, rax
0x14007156b  jz      loc_140071771
0x140071571  test    byte ptr [rcx+1Ch], 1
0x140071575  jz      loc_140071771
0x14007157b  mov     rcx, [rcx+10h]
0x14007157f  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140071586  mov     edx, 62h ; 'b'
0x14007158b  mov     r9d, ebx
0x14007158e  call    WPP_SF_d
0x140071593  jmp     loc_140071771
0x140071598  cmp     [rbp+57h+var_64], 1
0x14007159c  jz      short loc_1400715A8
0x14007159e  mov     ebx, 5
0x1400715a3  jmp     loc_140071771
0x1400715a8  mov     edx, 2
0x1400715ad  cmp     edi, edx
0x1400715af  jb      short loc_1400715EC
0x1400715b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400715b8  lea     rax, WPP_GLOBAL_Control
0x1400715bf  cmp     rcx, rax
0x1400715c2  jz      short loc_1400715E2
0x1400715c4  test    byte ptr [rcx+1Ch], 1
0x1400715c8  jz      short loc_1400715E2
0x1400715ca  mov     rcx, [rcx+10h]
0x1400715ce  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x1400715d5  mov     edx, 63h ; 'c'
0x1400715da  mov     r9d, edi
0x1400715dd  call    WPP_SF_d
0x1400715e2  mov     ebx, 57h ; 'W'
0x1400715e7  jmp     loc_140071771
0x1400715ec  mov     rcx, rsi; void *
0x1400715ef  call    ?ScIsValidScManagerHandle@@YAHPEAX@Z; ScIsValidScManagerHandle(void *)
0x1400715f4  test    eax, eax
0x1400715f6  jnz     short loc_140071630
0x1400715f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400715ff  lea     rax, WPP_GLOBAL_Control
0x140071606  cmp     rcx, rax
0x140071609  jz      short loc_140071626
0x14007160b  test    byte ptr [rcx+1Ch], 1
0x14007160f  jz      short loc_140071626
0x140071611  mov     rcx, [rcx+10h]
0x140071615  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x14007161c  mov     edx, 64h ; 'd'
0x140071621  call    WPP_SF_
0x140071626  mov     ebx, 6
0x14007162b  jmp     loc_140071771
0x140071630  mov     ecx, [rsi+8]; GrantedAccess
0x140071633  call    cs:__imp_RtlAreAllAccessesGranted
0x140071639  test    al, al
0x14007163b  jnz     short loc_140071678
0x14007163d  mov     rcx, cs:WPP_GLOBAL_Control
0x140071644  lea     rax, WPP_GLOBAL_Control
0x14007164b  cmp     rcx, rax
0x14007164e  jz      loc_14007159E
0x140071654  test    byte ptr [rcx+1Ch], 1
0x140071658  jz      loc_14007159E
0x14007165e  mov     rcx, [rcx+10h]
0x140071662  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140071669  mov     edx, 65h ; 'e'
0x14007166e  call    WPP_SF_
0x140071673  jmp     loc_14007159E
0x140071678  mov     rbx, [rbp+rdi*8+57h+var_B8]
0x14007167d  lea     rax, [rbp+57h+var_D0]
0x140071681  mov     rdx, rbx; unsigned __int16 *
0x140071684  mov     [rsp+100h+var_E0], rax; unsigned int *
0x140071689  lea     r9, [rbp+57h+var_C8]; unsigned __int8 **
0x14007168d  call    ?RegQueryValueWithAlloc@@YAKPEAUHKEY__@@PEBGKPEAPEAEPEAK@Z; RegQueryValueWithAlloc(HKEY__ *,ushort const *,ulong,uchar * *,ulong *)
0x140071692  mov     rsi, [rbp+57h+var_C8]
0x140071696  mov     r8d, eax
0x140071699  test    eax, eax
0x14007169b  jz      short loc_1400716DA
0x14007169d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400716a4  lea     rax, WPP_GLOBAL_Control
0x1400716ab  cmp     rcx, rax
0x1400716ae  jz      short loc_1400716D3
0x1400716b0  test    byte ptr [rcx+1Ch], 1
0x1400716b4  jz      short loc_1400716D3
0x1400716b6  mov     rcx, [rcx+10h]
0x1400716ba  mov     edx, 66h ; 'f'
0x1400716bf  mov     dword ptr [rsp+100h+var_E0], r8d
0x1400716c4  mov     r9, rbx
0x1400716c7  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x1400716ce  call    WPP_SF_Sd
0x1400716d3  mov     ebx, 57h ; 'W'
0x1400716d8  jmp     short loc_140071754
0x1400716da  mov     edx, [rbp+57h+var_D0]; unsigned int
0x1400716dd  lea     r9, [rbp+57h+var_CC]; unsigned int *
0x1400716e1  lea     r8, [rbp+57h+P]; struct _SC_REPARSE_INFO **
0x1400716e5  mov     rcx, rsi; unsigned __int16 *
0x1400716e8  call    ?ScGetReparseInfo@@YAKPEBGKPEAPEAU_SC_REPARSE_INFO@@PEAK@Z; ScGetReparseInfo(ushort const *,ulong,_SC_REPARSE_INFO * *,ulong *)
0x1400716ed  mov     rdi, [rbp+57h+P]
0x1400716f1  mov     ebx, eax
0x1400716f3  test    eax, eax
0x1400716f5  jz      short loc_14007172A
0x1400716f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400716fe  lea     rax, WPP_GLOBAL_Control
0x140071705  cmp     rcx, rax
0x140071708  jz      short loc_140071737
0x14007170a  test    byte ptr [rcx+1Ch], 1
0x14007170e  jz      short loc_140071737
0x140071710  mov     rcx, [rcx+10h]
0x140071714  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x14007171b  mov     edx, 67h ; 'g'
0x140071720  mov     r9d, ebx
0x140071723  call    WPP_SF_d
0x140071728  jmp     short loc_140071737
0x14007172a  mov     edx, [rbp+57h+var_CC]; unsigned int
0x14007172d  mov     rcx, rdi; struct _SC_REPARSE_INFO *
0x140071730  call    ?ScPerformReparse@@YAKPEAU_SC_REPARSE_INFO@@K@Z; ScPerformReparse(_SC_REPARSE_INFO *,ulong)
0x140071735  mov     ebx, eax
0x140071737  test    rdi, rdi
0x14007173a  jz      short loc_140071754
0x14007173c  mov     rcx, gs:60h
0x140071745  mov     r8, rdi; P
0x140071748  xor     edx, edx; Flags
0x14007174a  mov     rcx, [rcx+30h]; HeapHandle
0x14007174e  call    cs:__imp_RtlFreeHeap
0x140071754  test    rsi, rsi
0x140071757  jz      short loc_140071771
0x140071759  mov     rcx, gs:60h
0x140071762  mov     r8, rsi; P
0x140071765  xor     edx, edx; Flags
0x140071767  mov     rcx, [rcx+30h]; HeapHandle
0x14007176b  call    cs:__imp_RtlFreeHeap
0x140071771  mov     eax, ebx
0x140071773  mov     rcx, [rbp+57h+var_20]
0x140071777  xor     rcx, rsp; StackCookie
0x14007177a  call    __security_check_cookie
0x14007177f  mov     rbx, [rsp+100h+arg_10]
0x140071787  add     rsp, 0F0h
0x14007178e  pop     rdi
0x14007178f  pop     rsi
0x140071790  pop     rbp
0x140071791  retn
```
