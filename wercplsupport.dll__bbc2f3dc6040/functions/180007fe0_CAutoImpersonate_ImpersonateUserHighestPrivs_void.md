# CAutoImpersonate::ImpersonateUserHighestPrivs(void)

- ea: `0x180007fe0`
- end: `0x180008091`
- name: `?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ`
- size: `177`
- prototype: `__int64 __fastcall(CAutoImpersonate *__hidden this)`
- caller_count: `40`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000917c`
- `0x180009244`
- `0x18000a360`
- `0x18000a3c0`
- `0x18000a7a0`
- `0x18000aa40`
- `0x18000ae20`
- `0x18000ae80`
- `0x18000aee0`
- `0x18000af40`
- `0x18000afa0`
- `0x18000b000`
- `0x18000b050`
- `0x18000b570`
- `0x18000b730`
- `0x18000bd90`
- `0x18000c180`
- `0x180011120`
- `0x180011180`
- `0x1800111d0`
- `0x180011240`
- `0x180011310`
- `0x1800113e0`
- `0x180011440`
- `0x1800114a0`
- `0x180011500`
- `0x180011560`
- `0x1800115c0`
- `0x180011620`
- `0x1800116e0`
- `0x180011740`
- `0x1800117a0`
- `0x180011860`
- `0x180011920`
- `0x180011980`
- `0x1800119e0`
- `0x180011a40`
- `0x180011aa0`
- `0x180011b60`
- `0x180011bc0`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x180007dd8`
- `0x180007fe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180008036`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180008036`

## pseudocode

```c
__int64 __fastcall CAutoImpersonate::ImpersonateUserHighestPrivs(CAutoImpersonate *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  int v5; // edx

  if ( !CAutoImpersonate::g_bEnableImpersonate )
    return 0;
  if ( (int)ImpersonateProtectedAdminFullToken() >= 0 )
  {
    v5 = 0;
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids);
  v2 = CoImpersonateClient();
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = 1;
LABEL_13:
    *(_DWORD *)this = v5;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids, (unsigned int)v2);
  return v3;
}

```

## disassembly

```asm
0x180007fe0  mov     [rsp+arg_0], rbx
0x180007fe5  mov     [rsp+arg_8], rsi
0x180007fea  push    rdi
0x180007feb  sub     rsp, 20h
0x180007fef  cmp     cs:?g_bEnableImpersonate@CAutoImpersonate@@1HA, 0; int CAutoImpersonate::g_bEnableImpersonate
0x180007ff6  mov     rdi, rcx
0x180007ff9  jz      loc_18000807F
0x180007fff  call    ?ImpersonateProtectedAdminFullToken@@YAJXZ; ImpersonateProtectedAdminFullToken(void)
0x180008004  test    eax, eax
0x180008006  jns     short loc_18000807B
0x180008008  mov     rcx, cs:WPP_GLOBAL_Control
0x18000800f  lea     rsi, WPP_GLOBAL_Control
0x180008016  cmp     rcx, rsi
0x180008019  jz      short loc_180008036
0x18000801b  test    byte ptr [rcx+1Ch], 4
0x18000801f  jz      short loc_180008036
0x180008021  mov     rcx, [rcx+10h]
0x180008025  lea     r8, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids
0x18000802c  mov     edx, 11h
0x180008031  call    WPP_SF_
0x180008036  call    cs:__imp_CoImpersonateClient
0x18000803c  mov     ebx, eax
0x18000803e  test    eax, eax
0x180008040  jns     short loc_180008074
0x180008042  mov     rcx, cs:WPP_GLOBAL_Control
0x180008049  cmp     rcx, rsi
0x18000804c  jz      short loc_180008070
0x18000804e  mov     edx, 1
0x180008053  test    [rcx+1Ch], dl
0x180008056  jz      short loc_180008070
0x180008058  mov     rcx, [rcx+10h]
0x18000805c  lea     r8, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids
0x180008063  mov     edx, 12h
0x180008068  mov     r9d, eax
0x18000806b  call    WPP_SF_d
0x180008070  mov     eax, ebx
0x180008072  jmp     short loc_180008081
0x180008074  mov     edx, 1
0x180008079  jmp     short loc_18000807D
0x18000807b  xor     edx, edx
0x18000807d  mov     [rdi], edx
0x18000807f  xor     eax, eax
0x180008081  mov     rbx, [rsp+28h+arg_0]
0x180008086  mov     rsi, [rsp+28h+arg_8]
0x18000808b  add     rsp, 20h
0x18000808f  pop     rdi
0x180008090  retn
```
