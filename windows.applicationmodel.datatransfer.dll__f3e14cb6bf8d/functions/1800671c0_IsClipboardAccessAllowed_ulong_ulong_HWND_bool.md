# IsClipboardAccessAllowed(ulong,ulong,HWND__ *,bool)

- ea: `0x1800671c0`
- end: `0x180067296`
- name: `?IsClipboardAccessAllowed@@YA_NKKPEAUHWND__@@_N@Z`
- size: `214`
- prototype: `bool __fastcall(unsigned int, unsigned int, HWND, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800672a0`

## callees

- `0x180004388`
- `0x18005679c`
- `0x180066c70`
- `0x1800671c0`
- `0x180067b60`

## import_xrefs

- `RMCLIENT!RmAccessCheck` at `0x180067235`
- `RMCLIENT!RmAccessCheck` at `0x180067235`
- `api-ms-win-security-capability-l1-1-0!RpcClientCapabilityCheck` at `0x18006724f`
- `api-ms-win-security-capability-l1-1-0!RpcClientCapabilityCheck` at `0x18006724f`
- `ext-ms-win-ntuser-private-l1-3-1!CheckProcessForClipboardAccess` at `0x1800671f0`
- `ext-ms-win-ntuser-private-l1-3-1!CheckProcessForClipboardAccess` at `0x1800671f0`

## pseudocode

```c
char __fastcall IsClipboardAccessAllowed(__int64 a1, int a2, HWND a3, char a4)
{
  int v5; // esi
  unsigned int v7; // ebx
  const char *v8; // r9
  char v9; // bl
  int v10; // eax
  int v12; // [rsp+20h] [rbp-48h] BYREF
  _DWORD v13[16]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = (int)a3;
  v7 = a1;
  if ( (unsigned __int8)IsOleInitializePresent(a1) )
  {
    if ( !a4 )
      return 1;
    v12 = 0;
    if ( !(unsigned int)CheckProcessForClipboardAccess(v7, &v12) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboardpolicy.cpp",
        v8);
    if ( v12 )
    {
      return 1;
    }
    else
    {
      v13[0] = v7;
      v13[1] = a2;
      v13[2] = v5;
      v13[3] = 0;
      return ConnectToInputServerAndCheckAccess((const struct ClipboardCallerInfo *)v13);
    }
  }
  else
  {
    v10 = RmAccessCheck(28, v7);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboardpolicy.cpp",
        (const char *)(unsigned int)v10,
        v12);
    v9 = 1;
    if ( v10 == 1 )
      return (int)RpcClientCapabilityCheck(L"ID_CAP_CLIPBOARD") >= 0;
  }
  return v9;
}

```

## disassembly

```asm
0x1800671c0  push    rbx
0x1800671c2  push    rbp
0x1800671c3  push    rsi
0x1800671c4  push    rdi
0x1800671c5  sub     rsp, 48h
0x1800671c9  mov     dil, r9b
0x1800671cc  mov     rsi, r8
0x1800671cf  mov     ebp, edx
0x1800671d1  mov     ebx, ecx
0x1800671d3  call    IsOleInitializePresent
0x1800671d8  test    al, al
0x1800671da  jz      short loc_18006722E
0x1800671dc  test    dil, dil
0x1800671df  jz      short loc_180067227
0x1800671e1  lea     rdx, [rsp+68h+var_48]
0x1800671e6  mov     [rsp+68h+var_48], 0
0x1800671ee  mov     ecx, ebx
0x1800671f0  call    cs:__imp_CheckProcessForClipboardAccess
0x1800671f6  test    eax, eax
0x1800671f8  jz      loc_18006727F
0x1800671fe  cmp     [rsp+68h+var_48], 0
0x180067203  jnz     short loc_180067227
0x180067205  lea     rcx, [rsp+68h+var_40]; struct ClipboardCallerInfo *
0x18006720a  mov     [rsp+68h+var_40], ebx
0x18006720e  mov     [rsp+68h+var_3C], ebp
0x180067212  mov     [rsp+68h+var_38], esi
0x180067216  mov     [rsp+68h+var_34], 0
0x18006721e  call    ?ConnectToInputServerAndCheckAccess@@YA_NAEBUClipboardCallerInfo@@@Z; ConnectToInputServerAndCheckAccess(ClipboardCallerInfo const &)
0x180067223  mov     bl, al
0x180067225  jmp     short loc_18006725A
0x180067227  mov     ebx, 1
0x18006722c  jmp     short loc_18006725A
0x18006722e  mov     edx, ebx
0x180067230  mov     ecx, 1Ch
0x180067235  call    cs:__imp_RmAccessCheck
0x18006723b  test    eax, eax
0x18006723d  js      short loc_180067265
0x18006723f  mov     ebx, 1
0x180067244  cmp     eax, ebx
0x180067246  jnz     short loc_18006725A
0x180067248  lea     rcx, aIdCapClipboard; "ID_CAP_CLIPBOARD"
0x18006724f  call    cs:__imp_RpcClientCapabilityCheck
0x180067255  shr     eax, 1Fh
0x180067258  xor     bl, al
0x18006725a  mov     al, bl
0x18006725c  add     rsp, 48h
0x180067260  pop     rdi
0x180067261  pop     rsi
0x180067262  pop     rbp
0x180067263  pop     rbx
0x180067264  retn
0x180067265  mov     rcx, [rsp+68h]; this
0x18006726a  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180067271  mov     r9d, eax; char *
0x180067274  mov     edx, 59h ; 'Y'; void *
0x180067279  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006727f  mov     rcx, [rsp+68h]; this
0x180067284  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x18006728b  mov     edx, 3Fh ; '?'; void *
0x180067290  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
