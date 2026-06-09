# NetworkKeyControls::ShowKey(void)

- ea: `0x18000d464`
- end: `0x18000d669`
- name: `?ShowKey@NetworkKeyControls@@AEAAHXZ`
- size: `517`
- prototype: `__int64 __fastcall(HWND *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000b3a8`

## callees

- `0x180006588`
- `0x1800070e8`
- `0x18000d464`
- `0x18001bf40`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000d622`
- `KERNEL32!GetProcessHeap` at `0x18000d622`
- `KERNEL32!HeapFree` at `0x18000d630`
- `KERNEL32!HeapFree` at `0x18000d630`
- `USER32!SetWindowTextW` at `0x18000d5a9`
- `USER32!SetWindowTextW` at `0x18000d5ba`
- `USER32!SetWindowTextW` at `0x18000d5a9`
- `USER32!SetWindowTextW` at `0x18000d5ba`
- `USER32!ShowWindow` at `0x18000d5cd`
- `USER32!ShowWindow` at `0x18000d5d9`
- `USER32!ShowWindow` at `0x18000d5f3`
- `USER32!ShowWindow` at `0x18000d5cd`
- `USER32!ShowWindow` at `0x18000d5d9`
- `USER32!ShowWindow` at `0x18000d5f3`
- `USER32!GetDlgItem` at `0x18000d5e8`
- `USER32!GetDlgItem` at `0x18000d5e8`
- `wlanapi!WlanOpenHandle` at `0x18000d523`
- `wlanapi!WlanOpenHandle` at `0x18000d523`
- `wlanapi!WlanCloseHandle` at `0x18000d60f`
- `wlanapi!WlanCloseHandle` at `0x18000d60f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000d4e1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000d4e1`
- `ADVAPI32!CheckTokenMembership` at `0x18000d4f8`
- `ADVAPI32!CheckTokenMembership` at `0x18000d4f8`
- `ADVAPI32!FreeSid` at `0x18000d509`
- `ADVAPI32!FreeSid` at `0x18000d509`

## pseudocode

```c
__int64 __fastcall NetworkKeyControls::ShowKey(HWND *this)
{
  unsigned int v2; // edi
  const struct _GUID *v3; // rdx
  HWND v4; // rcx
  const struct _GUID *v5; // r8
  HWND v6; // rcx
  HWND DlgItem; // rax
  WCHAR *v8; // rbx
  HANDLE ProcessHeap; // rax
  WINBOOL IsMember; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v12; // [rsp+64h] [rbp-5h] BYREF
  LPCWSTR lpString; // [rsp+68h] [rbp-1h] BYREF
  void *phClientHandle; // [rsp+70h] [rbp+7h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+78h] [rbp+Fh] BYREF
  PSID SidToCheck; // [rsp+80h] [rbp+17h] BYREF
  void *v17; // [rsp+88h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+27h] BYREF

  v12 = 4;
  v17 = 0;
  v2 = 0;
  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  lpString = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  IsMember = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  if ( !IsMember )
    goto LABEL_9;
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    IsMember = 0;
  FreeSid(SidToCheck);
  if ( IsMember )
  {
    if ( !WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle)
      && !(unsigned int)WLUIGetProfileKey(
                          phClientHandle,
                          (const unsigned __int16 *)(*((_QWORD *)*this + 5) + 24LL),
                          *((struct _GUID **)*this + 2),
                          &v12,
                          (unsigned __int16 **)&lpString) )
    {
LABEL_10:
      SetWindowTextW(this[6], lpString);
      SetWindowTextW(this[4], &String);
      v6 = this[6];
      this[5] = v6;
      ShowWindow(v6, 5);
      ShowWindow(this[4], 0);
      DlgItem = GetDlgItem(this[2], 1134);
      ShowWindow(DlgItem, 0);
      v2 = 1;
      *((_DWORD *)this + 17) = 1;
      *((_DWORD *)this + 16) = 1;
    }
  }
  else
  {
LABEL_9:
    if ( CoCreateInstanceAsAdmin(v4, v3, v5, &v17) >= 0
      && (*(int (__fastcall **)(void *, __int64, _QWORD, unsigned int *, LPCWSTR *))(*(_QWORD *)v17 + 32LL))(
           v17,
           *((_QWORD *)*this + 5) + 24LL,
           *((_QWORD *)*this + 2),
           &v12,
           &lpString) >= 0 )
    {
      goto LABEL_10;
    }
  }
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    phClientHandle = 0;
  }
  v8 = (WCHAR *)lpString;
  if ( lpString )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    lpString = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
  return v2;
}

```

## disassembly

```asm
0x18000d464  push    rbp
0x18000d466  push    rbx
0x18000d467  push    rsi
0x18000d468  push    rdi
0x18000d469  lea     rbp, [rsp-3Fh]
0x18000d46e  sub     rsp, 0A8h
0x18000d475  mov     rax, cs:__security_cookie
0x18000d47c  xor     rax, rsp
0x18000d47f  mov     [rbp+57h+var_28], rax
0x18000d483  xor     esi, esi
0x18000d485  mov     [rbp+57h+var_5C], 4
0x18000d48c  lea     rax, [rbp+57h+SidToCheck]
0x18000d490  mov     [rbp+57h+var_38], rsi
0x18000d494  mov     [rsp+0C0h+pSid], rax; pSid
0x18000d499  mov     rbx, rcx
0x18000d49c  mov     [rsp+0C0h+nSubAuthority7], esi; nSubAuthority7
0x18000d4a0  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000d4a4  mov     [rsp+0C0h+nSubAuthority6], esi; nSubAuthority6
0x18000d4a8  lea     r8d, [rsi+20h]; nSubAuthority0
0x18000d4ac  mov     [rsp+0C0h+nSubAuthority5], esi; nSubAuthority5
0x18000d4b0  mov     r9d, 220h; nSubAuthority1
0x18000d4b6  mov     [rsp+0C0h+nSubAuthority4], esi; nSubAuthority4
0x18000d4ba  mov     dl, 2; nSubAuthorityCount
0x18000d4bc  mov     [rsp+0C0h+nSubAuthority3], esi; nSubAuthority3
0x18000d4c0  mov     edi, esi
0x18000d4c2  mov     [rsp+0C0h+nSubAuthority2], esi; nSubAuthority2
0x18000d4c6  mov     [rbp+57h+phClientHandle], rsi
0x18000d4ca  mov     [rbp+57h+pdwNegotiatedVersion], esi
0x18000d4cd  mov     [rbp+57h+lpString], rsi
0x18000d4d1  mov     [rbp+57h+IsMember], esi
0x18000d4d4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18000d4d7  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000d4dd  mov     [rbp+57h+SidToCheck], rsi
0x18000d4e1  call    cs:__imp_AllocateAndInitializeSid
0x18000d4e7  mov     [rbp+57h+IsMember], eax
0x18000d4ea  test    eax, eax
0x18000d4ec  jz      short loc_18000D560
0x18000d4ee  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18000d4f2  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000d4f6  xor     ecx, ecx; TokenHandle
0x18000d4f8  call    cs:__imp_CheckTokenMembership
0x18000d4fe  test    eax, eax
0x18000d500  jnz     short loc_18000D505
0x18000d502  mov     [rbp+57h+IsMember], esi
0x18000d505  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18000d509  call    cs:__imp_FreeSid
0x18000d50f  mov     eax, [rbp+57h+IsMember]
0x18000d512  test    eax, eax
0x18000d514  jz      short loc_18000D560
0x18000d516  xor     edx, edx; pReserved
0x18000d518  lea     r9, [rbp+57h+phClientHandle]; phClientHandle
0x18000d51c  lea     r8, [rbp+57h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18000d520  lea     ecx, [rdx+2]; dwClientVersion
0x18000d523  call    cs:__imp_WlanOpenHandle
0x18000d529  test    eax, eax
0x18000d52b  jnz     loc_18000D604
0x18000d531  mov     r8, [rbx]
0x18000d534  lea     rax, [rbp+57h+lpString]
0x18000d538  mov     rcx, [rbp+57h+phClientHandle]; void *
0x18000d53c  lea     r9, [rbp+57h+var_5C]; unsigned int *
0x18000d540  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; unsigned __int16 **
0x18000d545  mov     rdx, [r8+28h]
0x18000d549  mov     r8, [r8+10h]; struct _GUID *
0x18000d54d  add     rdx, 18h; unsigned __int16 *
0x18000d551  call    ?WLUIGetProfileKey@@YAKPEAXPEBGPEAU_GUID@@PEAKPEAPEAG@Z; WLUIGetProfileKey(void *,ushort const *,_GUID *,ulong *,ushort * *)
0x18000d556  test    eax, eax
0x18000d558  jnz     loc_18000D604
0x18000d55e  jmp     short loc_18000D5A1
0x18000d560  lea     r9, [rbp+57h+var_38]; void **
0x18000d564  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18000d569  test    eax, eax
0x18000d56b  js      loc_18000D604
0x18000d571  mov     r8, [rbx]
0x18000d574  lea     r9, [rbp+57h+lpString]
0x18000d578  mov     rcx, [rbp+57h+var_38]
0x18000d57c  mov     qword ptr [rsp+0C0h+nSubAuthority2], r9
0x18000d581  lea     r9, [rbp+57h+var_5C]
0x18000d585  mov     rdx, [r8+28h]
0x18000d589  mov     rax, [rcx]
0x18000d58c  add     rdx, 18h
0x18000d590  mov     r8, [r8+10h]
0x18000d594  mov     rax, [rax+20h]
0x18000d598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d59d  test    eax, eax
0x18000d59f  js      short loc_18000D604
0x18000d5a1  mov     rdx, [rbp+57h+lpString]; lpString
0x18000d5a5  mov     rcx, [rbx+30h]; hWnd
0x18000d5a9  call    cs:__imp_SetWindowTextW
0x18000d5af  mov     rcx, [rbx+20h]; hWnd
0x18000d5b3  lea     rdx, String; lpString
0x18000d5ba  call    cs:__imp_SetWindowTextW
0x18000d5c0  mov     rcx, [rbx+30h]; hWnd
0x18000d5c4  mov     edx, 5; nCmdShow
0x18000d5c9  mov     [rbx+28h], rcx
0x18000d5cd  call    cs:__imp_ShowWindow
0x18000d5d3  mov     rcx, [rbx+20h]; hWnd
0x18000d5d7  xor     edx, edx; nCmdShow
0x18000d5d9  call    cs:__imp_ShowWindow
0x18000d5df  mov     rcx, [rbx+10h]; hDlg
0x18000d5e3  mov     edx, 46Eh; nIDDlgItem
0x18000d5e8  call    cs:__imp_GetDlgItem
0x18000d5ee  mov     rcx, rax; hWnd
0x18000d5f1  xor     edx, edx; nCmdShow
0x18000d5f3  call    cs:__imp_ShowWindow
0x18000d5f9  mov     edi, 1
0x18000d5fe  mov     [rbx+44h], edi
0x18000d601  mov     [rbx+40h], edi
0x18000d604  mov     rcx, [rbp+57h+phClientHandle]; hClientHandle
0x18000d608  test    rcx, rcx
0x18000d60b  jz      short loc_18000D619
0x18000d60d  xor     edx, edx; pReserved
0x18000d60f  call    cs:__imp_WlanCloseHandle
0x18000d615  mov     [rbp+57h+phClientHandle], rsi
0x18000d619  mov     rbx, [rbp+57h+lpString]
0x18000d61d  test    rbx, rbx
0x18000d620  jz      short loc_18000D63A
0x18000d622  call    cs:__imp_GetProcessHeap
0x18000d628  mov     r8, rbx; lpMem
0x18000d62b  xor     edx, edx; dwFlags
0x18000d62d  mov     rcx, rax; hHeap
0x18000d630  call    cs:__imp_HeapFree
0x18000d636  mov     [rbp+57h+lpString], rsi
0x18000d63a  mov     rcx, [rbp+57h+var_38]
0x18000d63e  test    rcx, rcx
0x18000d641  jz      short loc_18000D64F
0x18000d643  mov     rdx, [rcx]
0x18000d646  mov     rax, [rdx+10h]
0x18000d64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d64f  mov     eax, edi
0x18000d651  mov     rcx, [rbp+57h+var_28]
0x18000d655  xor     rcx, rsp; StackCookie
0x18000d658  call    __security_check_cookie
0x18000d65d  add     rsp, 0A8h
0x18000d664  pop     rdi
0x18000d665  pop     rsi
0x18000d666  pop     rbx
0x18000d667  pop     rbp
0x18000d668  retn
```
