# RpcGetProfile

- ea: `0x18003e120`
- end: `0x18003e4b9`
- name: `RpcGetProfile`
- size: `921`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, const unsigned __int16 *, unsigned __int16 **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003c4b0`
- `0x18003e120`
- `0x18003e4c0`
- `0x18003e670`
- `0x180103e24`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e40b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e40b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e23a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e339`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e23a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e339`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e224`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e224`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e24a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e24a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003e206`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003e206`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall RpcGetProfile(
        __int64 a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned int *a5,
        unsigned int *a6)
{
  unsigned int v10; // eax
  PSID v11; // rsi
  unsigned int ProfileXml; // ebx
  PVOID *v13; // rcx
  unsigned int v14; // eax
  HANDLE v15; // rbx
  DWORD LastError; // edi
  PVOID *v17; // rcx
  bool v18; // zf
  volatile signed __int32 *v19; // rdi
  std::_Ref_count_base *v20; // rdx
  unsigned int v21; // r10d
  signed __int32 v22; // eax
  signed __int32 v23; // ett
  PSID Sid; // [rsp+50h] [rbp-58h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-50h] BYREF
  WINBOOL IsMember; // [rsp+B0h] [rbp+8h] BYREF

  Sid = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 153, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  }
  v10 = LocalQueryRpcClientToken(&Sid);
  v11 = Sid;
  ProfileXml = v10;
  if ( !v10 )
  {
    if ( a2 && a3 && a4 )
    {
      if ( byte_1802A2E08 )
      {
        IsMember = 0;
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 51, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
        TokenHandle = 0;
        Sid = 0;
        if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 105) >= 4u && (*((_BYTE *)v13 + 108) & 1) != 0 )
          WPP_SF_(v13[12], 47, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
        IsMember = 0;
        v14 = LocalQueryRpcClientToken(&TokenHandle);
        v15 = TokenHandle;
        LastError = v14;
        if ( !v14
          && (ConvertStringSidToSidW(L"S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142", &Sid)
           || (LastError = GetLastError()) == 0)
          && !CheckTokenMembership(v15, Sid, &IsMember) )
        {
          LastError = GetLastError();
        }
        if ( v15 )
          CloseHandle(v15);
        if ( Sid )
          LocalFree(Sid);
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              48,
              &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids,
              LastError);
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 105) >= 4u && (*((_BYTE *)v17 + 108) & 1) != 0 )
            WPP_SF_d(v17[12], 52, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
        }
        v18 = IsMember == 0;
        v19 = 0;
        *a4 = 0;
        v20 = qword_1802A4AB0;
        if ( qword_1802A4AB0 )
        {
          v21 = *(_DWORD *)(a1 + 384);
          v22 = *((_DWORD *)qword_1802A4AB0 + 2);
          while ( v22 )
          {
            v23 = v22;
            v22 = _InterlockedCompareExchange((volatile signed __int32 *)v20 + 2, v22 + 1, v22);
            if ( v23 == v22 )
            {
              v19 = (volatile signed __int32 *)qword_1802A4AB0;
              if ( !qword_1802A4AA8 )
                break;
              ProfileXml = ProfileManager::GetProfileXml(qword_1802A4AA8, v11, v21, a2, 0x25u, a3, !v18, a4, a5, a6);
              if ( v19 && _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
                std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v19);
              }
              goto LABEL_32;
            }
          }
        }
        if ( v19 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v19);
        ProfileXml = 21;
      }
      else
      {
        ProfileXml = 1722;
      }
    }
    else
    {
      ProfileXml = 87;
    }
  }
LABEL_32:
  if ( v11 )
    CloseHandle(v11);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 154, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, ProfileXml);
  }
  return ProfileXml;
}

```

## disassembly

```asm
0x18003e120  push    rbx
0x18003e122  push    rbp
0x18003e123  push    rsi
0x18003e124  push    rdi
0x18003e125  push    r12
0x18003e127  push    r13
0x18003e129  push    r14
0x18003e12b  push    r15
0x18003e12d  sub     rsp, 68h
0x18003e131  xor     r13d, r13d
0x18003e134  mov     r14, r9
0x18003e137  mov     [rsp+0A8h+Sid], r13
0x18003e13c  mov     r15, r8
0x18003e13f  mov     r12, rdx
0x18003e142  mov     rbp, rcx
0x18003e145  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e14c  lea     rdi, WPP_GLOBAL_Control
0x18003e153  cmp     rcx, rdi
0x18003e156  jz      short loc_18003E162
0x18003e158  cmp     byte ptr [rcx+69h], 4
0x18003e15c  jnb     loc_18003E383
0x18003e162  lea     rcx, [rsp+0A8h+Sid]; void **
0x18003e167  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003e16c  mov     rsi, [rsp+0A8h+Sid]
0x18003e171  mov     ebx, eax
0x18003e173  test    eax, eax
0x18003e175  jnz     loc_18003E331
0x18003e17b  test    r12, r12
0x18003e17e  jz      loc_18003E488
0x18003e184  test    r15, r15
0x18003e187  jz      loc_18003E488
0x18003e18d  test    r14, r14
0x18003e190  jz      loc_18003E488
0x18003e196  movzx   eax, cs:byte_1802A2E08
0x18003e19d  nop
0x18003e19e  test    al, al
0x18003e1a0  jz      loc_18003E37C
0x18003e1a6  mov     [rsp+0A8h+IsMember], r13d
0x18003e1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e1b5  cmp     rcx, rdi
0x18003e1b8  jz      short loc_18003E1C4
0x18003e1ba  cmp     byte ptr [rcx+69h], 4
0x18003e1be  jnb     loc_18003E3A7
0x18003e1c4  mov     [rsp+0A8h+TokenHandle], r13
0x18003e1c9  mov     [rsp+0A8h+Sid], r13
0x18003e1ce  cmp     rcx, rdi
0x18003e1d1  jz      short loc_18003E1DD
0x18003e1d3  cmp     byte ptr [rcx+69h], 4
0x18003e1d7  jnb     loc_18003E3D2
0x18003e1dd  lea     rcx, [rsp+0A8h+TokenHandle]; void **
0x18003e1e2  mov     [rsp+0A8h+IsMember], r13d
0x18003e1ea  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003e1ef  mov     rbx, [rsp+0A8h+TokenHandle]
0x18003e1f4  mov     edi, eax
0x18003e1f6  test    eax, eax
0x18003e1f8  jnz     short loc_18003E232
0x18003e1fa  lea     rdx, [rsp+0A8h+Sid]; Sid
0x18003e1ff  lea     rcx, aS1580142802753; "S-1-5-80-1428027539-3309602793-26783530"...
0x18003e206  call    cs:__imp_ConvertStringSidToSidW
0x18003e20c  test    eax, eax
0x18003e20e  jz      loc_18003E3F6
0x18003e214  mov     rdx, [rsp+0A8h+Sid]; SidToCheck
0x18003e219  lea     r8, [rsp+0A8h+IsMember]; IsMember
0x18003e221  mov     rcx, rbx; TokenHandle
0x18003e224  call    cs:__imp_CheckTokenMembership
0x18003e22a  test    eax, eax
0x18003e22c  jz      loc_18003E40B
0x18003e232  test    rbx, rbx
0x18003e235  jz      short loc_18003E240
0x18003e237  mov     rcx, rbx; hObject
0x18003e23a  call    cs:__imp_CloseHandle
0x18003e240  mov     rcx, [rsp+0A8h+Sid]; hMem
0x18003e245  test    rcx, rcx
0x18003e248  jz      short loc_18003E250
0x18003e24a  call    cs:__imp_LocalFree
0x18003e250  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e257  lea     rbx, WPP_GLOBAL_Control
0x18003e25e  cmp     rcx, rbx
0x18003e261  jz      short loc_18003E27C
0x18003e263  cmp     byte ptr [rcx+69h], 4
0x18003e267  jnb     loc_18003E418
0x18003e26d  cmp     rcx, rbx
0x18003e270  jz      short loc_18003E27C
0x18003e272  cmp     byte ptr [rcx+69h], 4
0x18003e276  jnb     loc_18003E446
0x18003e27c  cmp     [rsp+0A8h+IsMember], r13d
0x18003e284  mov     rdi, r13
0x18003e287  mov     [r14], r13
0x18003e28a  mov     rdx, cs:qword_1802A4AB0
0x18003e291  setnz   r8b
0x18003e295  test    rdx, rdx
0x18003e298  jz      loc_18003E368
0x18003e29e  mov     r10d, [rbp+180h]
0x18003e2a5  mov     eax, [rdx+8]
0x18003e2a8  test    eax, eax
0x18003e2aa  jz      loc_18003E368
0x18003e2b0  lea     ecx, [rax+1]
0x18003e2b3  lock cmpxchg [rdx+8], ecx
0x18003e2b8  jnz     short loc_18003E2A8
0x18003e2ba  mov     rcx, cs:qword_1802A4AA8; lpCriticalSection
0x18003e2c1  mov     rdi, cs:qword_1802A4AB0
0x18003e2c8  test    rcx, rcx
0x18003e2cb  jz      loc_18003E368
0x18003e2d1  mov     rax, [rsp+0A8h+arg_28]
0x18003e2d9  mov     r9, r12; struct _GUID *
0x18003e2dc  mov     [rsp+0A8h+var_60], rax; unsigned int *
0x18003e2e1  mov     rdx, rsi; void *
0x18003e2e4  mov     rax, [rsp+0A8h+arg_20]
0x18003e2ec  mov     [rsp+0A8h+var_68], rax; unsigned int *
0x18003e2f1  mov     [rsp+0A8h+var_70], r14; unsigned __int16 **
0x18003e2f6  mov     [rsp+0A8h+var_78], r8b; bool
0x18003e2fb  mov     r8d, r10d; unsigned int
0x18003e2fe  mov     [rsp+0A8h+var_80], r15; unsigned __int16 *
0x18003e303  mov     [rsp+0A8h+var_88], 25h ; '%'; unsigned int
0x18003e30b  call    ?GetProfileXml@ProfileManager@@QEAAKPEAXKPEBU_GUID@@KPEBG_NPEAPEAGPEAK5@Z; ProfileManager::GetProfileXml(void *,ulong,_GUID const *,ulong,ushort const *,bool,ushort * *,ulong *,ulong *)
0x18003e310  mov     ebx, eax
0x18003e312  test    rdi, rdi
0x18003e315  jz      short loc_18003E32A
0x18003e317  mov     eax, 0FFFFFFFFh
0x18003e31c  lock xadd [rdi+8], eax
0x18003e321  cmp     eax, 1
0x18003e324  jz      loc_18003E46D
0x18003e32a  lea     rdi, WPP_GLOBAL_Control
0x18003e331  test    rsi, rsi
0x18003e334  jz      short loc_18003E33F
0x18003e336  mov     rcx, rsi; hObject
0x18003e339  call    cs:__imp_CloseHandle
0x18003e33f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e346  cmp     rcx, rdi
0x18003e349  jz      short loc_18003E355
0x18003e34b  cmp     byte ptr [rcx+69h], 4
0x18003e34f  jnb     loc_18003E492
0x18003e355  mov     eax, ebx
0x18003e357  add     rsp, 68h
0x18003e35b  pop     r15
0x18003e35d  pop     r14
0x18003e35f  pop     r13
0x18003e361  pop     r12
0x18003e363  pop     rdi
0x18003e364  pop     rsi
0x18003e365  pop     rbp
0x18003e366  pop     rbx
0x18003e367  retn
0x18003e368  test    rdi, rdi
0x18003e36b  jz      short loc_18003E375
0x18003e36d  mov     rcx, rdi; this
0x18003e370  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e375  mov     ebx, 15h
0x18003e37a  jmp     short loc_18003E32A
0x18003e37c  mov     ebx, 6BAh
0x18003e381  jmp     short loc_18003E331
0x18003e383  test    byte ptr [rcx+6Ch], 1
0x18003e387  jz      loc_18003E162
0x18003e38d  mov     rcx, [rcx+60h]
0x18003e391  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e398  mov     edx, 99h
0x18003e39d  call    WPP_SF_
0x18003e3a2  jmp     loc_18003E162
0x18003e3a7  test    byte ptr [rcx+6Ch], 1
0x18003e3ab  jz      loc_18003E1C4
0x18003e3b1  mov     rcx, [rcx+60h]
0x18003e3b5  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e3bc  mov     edx, 33h ; '3'
0x18003e3c1  call    WPP_SF_
0x18003e3c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3cd  jmp     loc_18003E1C4
0x18003e3d2  test    byte ptr [rcx+6Ch], 1
0x18003e3d6  jz      loc_18003E1DD
0x18003e3dc  mov     rcx, [rcx+60h]
0x18003e3e0  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e3e7  mov     edx, 2Fh ; '/'
0x18003e3ec  call    WPP_SF_
0x18003e3f1  jmp     loc_18003E1DD
0x18003e3f6  call    cs:__imp_GetLastError
0x18003e3fc  mov     edi, eax
0x18003e3fe  test    eax, eax
0x18003e400  jnz     loc_18003E232
0x18003e406  jmp     loc_18003E214
0x18003e40b  call    cs:__imp_GetLastError
0x18003e411  mov     edi, eax
0x18003e413  jmp     loc_18003E232
0x18003e418  test    byte ptr [rcx+6Ch], 1
0x18003e41c  jz      loc_18003E26D
0x18003e422  mov     rcx, [rcx+60h]
0x18003e426  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e42d  mov     edx, 30h ; '0'
0x18003e432  mov     r9d, edi
0x18003e435  call    WPP_SF_d
0x18003e43a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e441  jmp     loc_18003E26D
0x18003e446  test    byte ptr [rcx+6Ch], 1
0x18003e44a  jz      loc_18003E27C
0x18003e450  mov     rcx, [rcx+60h]
0x18003e454  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e45b  mov     edx, 34h ; '4'
0x18003e460  mov     r9d, edi
0x18003e463  call    WPP_SF_d
0x18003e468  jmp     loc_18003E27C
0x18003e46d  mov     rax, [rdi]
0x18003e470  mov     rcx, rdi
0x18003e473  mov     rax, [rax]
0x18003e476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e47b  mov     rcx, rdi; this
0x18003e47e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18003e483  jmp     loc_18003E32A
0x18003e488  mov     ebx, 57h ; 'W'
0x18003e48d  jmp     loc_18003E331
0x18003e492  test    byte ptr [rcx+6Ch], 1
0x18003e496  jz      loc_18003E355
0x18003e49c  mov     rcx, [rcx+60h]
0x18003e4a0  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e4a7  mov     edx, 9Ah
0x18003e4ac  mov     r9d, ebx
0x18003e4af  call    WPP_SF_d
0x18003e4b4  jmp     loc_18003E355
```
