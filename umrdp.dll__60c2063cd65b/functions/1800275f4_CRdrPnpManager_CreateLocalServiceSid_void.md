# CRdrPnpManager::CreateLocalServiceSid(void * *)

- ea: `0x1800275f4`
- end: `0x180027718`
- name: `?CreateLocalServiceSid@CRdrPnpManager@@CAJPEAPEAX@Z`
- size: `292`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029320`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x18001ba64`
- `0x1800275f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002768b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002768b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002760f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002760f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800276fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800276fa`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180027681`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180027681`

## string_xrefs

- `0x1800276c8`: `CreateWellKnownSid`

## pseudocode

```c
__int64 __fastcall CRdrPnpManager::CreateLocalServiceSid(void **a1)
{
  HLOCAL v1; // rax
  void *v2; // rdi
  unsigned int v3; // eax
  signed int v4; // ebx
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD cbSid; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+44h] [rbp+Ch]

  v9 = HIDWORD(a1);
  cbSid = 68;
  v1 = LocalAlloc(0x40u, 0x44u);
  v2 = v1;
  if ( v1 )
  {
    if ( CreateWellKnownSid(WinLocalServiceSid, 0, v1, &cbSid) )
    {
      v4 = 0;
      CRdrPnpManager::static_pLocalServiceSid = v2;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            28,
            (unsigned int)WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"CreateWellKnownSid",
            v4);
        }
        LocalFree(v2);
      }
    }
  }
  else
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        27,
        (unsigned int)WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
        v3,
        (__int64)"LPTR");
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800275f4  mov     [rsp+arg_8], rbx
0x1800275f9  mov     qword ptr [rsp+cbSid], rcx
0x1800275fe  push    rdi
0x1800275ff  sub     rsp, 30h
0x180027603  mov     edx, 44h ; 'D'; uBytes
0x180027608  mov     [rsp+38h+cbSid], edx
0x18002760c  lea     ecx, [rdx-4]; uFlags
0x18002760f  call    cs:__imp_LocalAlloc
0x180027615  mov     rdi, rax
0x180027618  test    rax, rax
0x18002761b  jnz     short loc_180027674
0x18002761d  mov     rax, cs:WPP_GLOBAL_Control
0x180027624  lea     rcx, WPP_GLOBAL_Control
0x18002762b  cmp     rax, rcx
0x18002762e  jz      short loc_18002766A
0x180027630  test    byte ptr [rax+1Ch], 8
0x180027634  jz      short loc_18002766A
0x180027636  cmp     byte ptr [rax+19h], 2
0x18002763a  jb      short loc_18002766A
0x18002763c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027641  lea     rcx, aLptr; "LPTR"
0x180027648  mov     r9d, eax
0x18002764b  mov     [rsp+38h+var_18], rcx
0x180027650  lea     edx, [rdi+1Bh]
0x180027653  mov     rcx, cs:WPP_GLOBAL_Control
0x18002765a  lea     r8, WPP_94246e01360c359abb577584ca0bcde6_Traceguids
0x180027661  mov     rcx, [rcx+10h]
0x180027665  call    WPP_SF_Ds
0x18002766a  mov     ebx, 8007000Eh
0x18002766f  jmp     loc_18002770B
0x180027674  xor     edx, edx; DomainSid
0x180027676  lea     r9, [rsp+38h+cbSid]; cbSid
0x18002767b  mov     r8, rdi; pSid
0x18002767e  lea     ecx, [rdx+17h]; WellKnownSidType
0x180027681  call    cs:__imp_CreateWellKnownSid
0x180027687  test    eax, eax
0x180027689  jnz     short loc_180027702
0x18002768b  call    cs:__imp_GetLastError
0x180027691  mov     ebx, eax
0x180027693  test    eax, eax
0x180027695  jle     short loc_1800276A0
0x180027697  movzx   ebx, ax
0x18002769a  or      ebx, 80070000h
0x1800276a0  test    ebx, ebx
0x1800276a2  jns     short loc_18002770B
0x1800276a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800276ab  lea     rcx, WPP_GLOBAL_Control
0x1800276b2  cmp     rax, rcx
0x1800276b5  jz      short loc_1800276F7
0x1800276b7  test    byte ptr [rax+1Ch], 8
0x1800276bb  jz      short loc_1800276F7
0x1800276bd  cmp     byte ptr [rax+19h], 2
0x1800276c1  jb      short loc_1800276F7
0x1800276c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800276c8  lea     rcx, aCreatewellknow; "CreateWellKnownSid"
0x1800276cf  mov     [rsp+38h+var_10], ebx
0x1800276d3  mov     [rsp+38h+var_18], rcx
0x1800276d8  lea     r8, WPP_94246e01360c359abb577584ca0bcde6_Traceguids
0x1800276df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276e6  mov     edx, 1Ch
0x1800276eb  mov     r9d, eax
0x1800276ee  mov     rcx, [rcx+10h]
0x1800276f2  call    WPP_SF_DsD
0x1800276f7  mov     rcx, rdi; hMem
0x1800276fa  call    cs:__imp_LocalFree
0x180027700  jmp     short loc_18002770B
0x180027702  xor     ebx, ebx
0x180027704  mov     cs:?static_pLocalServiceSid@CRdrPnpManager@@0PEAXEA, rdi; void * CRdrPnpManager::static_pLocalServiceSid
0x18002770b  mov     eax, ebx
0x18002770d  mov     rbx, [rsp+38h+arg_8]
0x180027712  add     rsp, 30h
0x180027716  pop     rdi
0x180027717  retn
```
