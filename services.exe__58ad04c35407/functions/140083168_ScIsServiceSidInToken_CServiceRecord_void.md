# ScIsServiceSidInToken(CServiceRecord *,void *)

- ea: `0x140083168`
- end: `0x14008333f`
- name: `?ScIsServiceSidInToken@@YAHPEAVCServiceRecord@@PEAX@Z`
- size: `471`
- prototype: `int(struct CServiceRecord *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003c510`

## callees

- `0x140003e54`
- `0x1400157bc`
- `0x1400188fc`
- `0x140030a5c`
- `0x140083168`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1400832b7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1400832b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140083306`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140083306`
- `ntdll!RtlNtStatusToDosError` at `0x140083260`
- `ntdll!RtlNtStatusToDosError` at `0x140083260`
- `ntdll!RtlFreeHeap` at `0x140083323`
- `ntdll!RtlFreeHeap` at `0x140083323`

## pseudocode

```c
__int64 __fastcall ScIsServiceSidInToken(struct CServiceRecord *a1, void *a2)
{
  int v2; // eax
  unsigned int v4; // ebp
  int TokenInformation; // eax
  _DWORD *v6; // rsi
  const WCHAR *v7; // rcx
  NTSTATUS v8; // eax
  char v9; // r8
  int v10; // edi
  PSID pSid2; // [rsp+50h] [rbp+8h] BYREF
  PVOID P; // [rsp+60h] [rbp+18h] BYREF

  v2 = *((_DWORD *)a1 + 13);
  P = 0;
  pSid2 = 0;
  if ( (v2 & 0x40) != 0 )
  {
    v4 = 0;
    if ( a2 )
    {
      TokenInformation = ScGetTokenInformation(a2, TokenGroups, &P);
      v6 = P;
      if ( TokenInformation )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            99,
            (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
            *((_QWORD *)a1 + 7),
            TokenInformation);
        }
      }
      else
      {
        v7 = (const WCHAR *)*((_QWORD *)a1 + 9);
        if ( !v7 )
          v7 = (const WCHAR *)*((_QWORD *)a1 + 7);
        v8 = ScCreateServiceSidFromString(v7, &pSid2);
        if ( v8 >= 0 )
        {
          v10 = 0;
          if ( *v6 )
          {
            while ( !EqualSid(*(PSID *)&v6[4 * v10 + 2], pSid2) )
            {
              if ( (unsigned int)++v10 >= *v6 )
                goto LABEL_20;
            }
            v4 = 1;
          }
          else
          {
LABEL_20:
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_S(
                WPP_GLOBAL_Control->StubInfo,
                101,
                WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
                *((_QWORD *)a1 + 7));
            }
          }
        }
        else
        {
          v9 = RtlNtStatusToDosError(v8);
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              100,
              (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              *((_QWORD *)a1 + 7),
              v9);
          }
        }
        if ( pSid2 )
          LocalFree(pSid2);
      }
      if ( v6 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    }
    else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
           && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 98, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, *((_QWORD *)a1 + 7));
    }
  }
  else
  {
    return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x140083168  mov     [rsp+arg_8], rbx
0x14008316d  push    rbp
0x14008316e  push    rsi
0x14008316f  push    rdi
0x140083170  sub     rsp, 30h
0x140083174  mov     eax, [rcx+34h]
0x140083177  mov     r9, rdx
0x14008317a  mov     [rsp+48h+P], 0
0x140083183  mov     rbx, rcx
0x140083186  mov     [rsp+48h+pSid2], 0
0x14008318f  test    al, 40h
0x140083191  jnz     short loc_14008319D
0x140083193  mov     ebp, 1
0x140083198  jmp     loc_140083329
0x14008319d  xor     ebp, ebp
0x14008319f  test    r9, r9
0x1400831a2  jnz     short loc_1400831E1
0x1400831a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400831ab  lea     rax, WPP_GLOBAL_Control
0x1400831b2  cmp     rcx, rax
0x1400831b5  jz      loc_140083329
0x1400831bb  test    byte ptr [rcx+1Ch], 1
0x1400831bf  jz      loc_140083329
0x1400831c5  mov     r9, [rbx+38h]
0x1400831c9  lea     edx, [rbp+62h]
0x1400831cc  mov     rcx, [rcx+10h]
0x1400831d0  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x1400831d7  call    WPP_SF_S
0x1400831dc  jmp     loc_140083329
0x1400831e1  lea     r8, [rsp+48h+P]; void **
0x1400831e6  mov     edx, 2; TokenInformationClass
0x1400831eb  mov     rcx, r9; TokenHandle
0x1400831ee  call    ?ScGetTokenInformation@@YAKPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; ScGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x1400831f3  mov     rsi, [rsp+48h+P]
0x1400831f8  mov     r8d, eax
0x1400831fb  test    eax, eax
0x1400831fd  jz      short loc_140083243
0x1400831ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140083206  lea     rax, WPP_GLOBAL_Control
0x14008320d  cmp     rcx, rax
0x140083210  jz      loc_14008330C
0x140083216  test    byte ptr [rcx+1Ch], 1
0x14008321a  jz      loc_14008330C
0x140083220  mov     r9, [rbx+38h]
0x140083224  mov     edx, 63h ; 'c'
0x140083229  mov     rcx, [rcx+10h]
0x14008322d  mov     [rsp+48h+var_28], r8d
0x140083232  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x140083239  call    WPP_SF_Sd
0x14008323e  jmp     loc_14008330C
0x140083243  mov     rcx, [rbx+48h]
0x140083247  test    rcx, rcx
0x14008324a  jnz     short loc_140083250
0x14008324c  mov     rcx, [rbx+38h]; SourceString
0x140083250  lea     rdx, [rsp+48h+pSid2]
0x140083255  call    ScCreateServiceSidFromString
0x14008325a  test    eax, eax
0x14008325c  jns     short loc_1400832A2
0x14008325e  mov     ecx, eax; Status
0x140083260  call    cs:__imp_RtlNtStatusToDosError
0x140083266  mov     r8d, eax
0x140083269  mov     rcx, cs:WPP_GLOBAL_Control
0x140083270  lea     rax, WPP_GLOBAL_Control
0x140083277  cmp     rcx, rax
0x14008327a  jz      short loc_1400832F9
0x14008327c  test    byte ptr [rcx+1Ch], 1
0x140083280  jz      short loc_1400832F9
0x140083282  mov     r9, [rbx+38h]
0x140083286  mov     edx, 64h ; 'd'
0x14008328b  mov     rcx, [rcx+10h]
0x14008328f  mov     [rsp+48h+var_28], r8d
0x140083294  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14008329b  call    WPP_SF_Sd
0x1400832a0  jmp     short loc_1400832F9
0x1400832a2  xor     edi, edi
0x1400832a4  cmp     [rsi], edi
0x1400832a6  jbe     short loc_1400832C7
0x1400832a8  mov     rdx, [rsp+48h+pSid2]; pSid2
0x1400832ad  mov     ecx, edi
0x1400832af  add     rcx, rcx
0x1400832b2  mov     rcx, [rsi+rcx*8+8]; pSid1
0x1400832b7  call    cs:__imp_EqualSid
0x1400832bd  test    eax, eax
0x1400832bf  jnz     short loc_140083338
0x1400832c1  inc     edi
0x1400832c3  cmp     edi, [rsi]
0x1400832c5  jb      short loc_1400832A8
0x1400832c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400832ce  lea     rax, WPP_GLOBAL_Control
0x1400832d5  cmp     rcx, rax
0x1400832d8  jz      short loc_1400832F9
0x1400832da  test    byte ptr [rcx+1Ch], 1
0x1400832de  jz      short loc_1400832F9
0x1400832e0  mov     r9, [rbx+38h]
0x1400832e4  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x1400832eb  mov     rcx, [rcx+10h]
0x1400832ef  mov     edx, 65h ; 'e'
0x1400832f4  call    WPP_SF_S
0x1400832f9  cmp     [rsp+48h+pSid2], 0
0x1400832ff  jz      short loc_14008330C
0x140083301  mov     rcx, [rsp+48h+pSid2]; hMem
0x140083306  call    cs:__imp_LocalFree
0x14008330c  test    rsi, rsi
0x14008330f  jz      short loc_140083329
0x140083311  mov     rcx, gs:60h
0x14008331a  mov     r8, rsi; P
0x14008331d  xor     edx, edx; Flags
0x14008331f  mov     rcx, [rcx+30h]; HeapHandle
0x140083323  call    cs:__imp_RtlFreeHeap
0x140083329  mov     rbx, [rsp+48h+arg_8]
0x14008332e  mov     eax, ebp
0x140083330  add     rsp, 30h
0x140083334  pop     rdi
0x140083335  pop     rsi
0x140083336  pop     rbp
0x140083337  retn
0x140083338  mov     ebp, 1
0x14008333d  jmp     short loc_1400832F9
```
