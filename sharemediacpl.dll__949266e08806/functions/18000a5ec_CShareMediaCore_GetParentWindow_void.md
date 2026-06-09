# CShareMediaCore::GetParentWindow(void)

- ea: `0x18000a5ec`
- end: `0x18000a704`
- name: `?GetParentWindow@CShareMediaCore@@QEAAPEAUHWND__@@XZ`
- size: `280`
- prototype: `HWND __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000ec90`
- `0x18000f660`
- `0x18000f95c`
- `0x180010590`
- `0x180010bec`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000a5ec`
- `0x18001e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000a6ac`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000a6ac`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000a698`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000a698`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000a66d`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000a66d`

## pseudocode

```c
HWND __fastcall CShareMediaCore::GetParentWindow(CShareMediaCore *this)
{
  _QWORD *v2; // rcx
  HRESULT Site; // ebx
  IUnknown *v4; // rcx
  void *ppvOut; // [rsp+40h] [rbp+8h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  Site = 0;
  if ( !*((_QWORD *)this + 3) )
  {
    if ( *((_QWORD *)this + 4)
      || (Site = IUnknown_GetSite(
                   (IUnknown *)((*((_QWORD *)this + 2) + 208LL) & -(__int64)(*((_QWORD *)this + 2) != 0)),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   (void **)this + 4),
          Site >= 0) )
    {
      v4 = (IUnknown *)*((_QWORD *)this + 4);
      ppvOut = 0;
      Site = IUnknown_QueryService(
               v4,
               (const GUID *const)&SID_STopLevelBrowser,
               &GUID_00000000_0000_0000_c000_000000000046,
               &ppvOut);
      if ( Site >= 0 )
      {
        IUnknown_GetWindow((IUnknown *)ppvOut, (HWND *)this + 3);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      }
    }
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 89, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, (unsigned int)Site);
  return (HWND)*((_QWORD *)this + 3);
}

```

## disassembly

```asm
0x18000a5ec  mov     [rsp+arg_8], rbx
0x18000a5f1  mov     [rsp+arg_10], rsi
0x18000a5f6  push    rdi
0x18000a5f7  push    r14
0x18000a5f9  push    r15
0x18000a5fb  sub     rsp, 20h
0x18000a5ff  mov     rsi, rcx
0x18000a602  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a609  lea     r15, WPP_GLOBAL_Control
0x18000a610  cmp     rcx, r15
0x18000a613  jz      short loc_18000A637
0x18000a615  test    byte ptr [rcx+1Ch], 20h
0x18000a619  jz      short loc_18000A637
0x18000a61b  mov     rcx, [rcx+10h]
0x18000a61f  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000a626  mov     edx, 58h ; 'X'
0x18000a62b  call    WPP_SF_
0x18000a630  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a637  xor     ebx, ebx
0x18000a639  lea     rdi, [rsi+18h]
0x18000a63d  cmp     [rdi], rbx
0x18000a640  jnz     loc_18000A6CA
0x18000a646  lea     r14, [rsi+20h]
0x18000a64a  cmp     [r14], rbx
0x18000a64d  jnz     short loc_18000A679
0x18000a64f  mov     rax, [rsi+10h]
0x18000a653  mov     r8, r14; ppv
0x18000a656  lea     rdx, [rax+0D0h]
0x18000a65d  neg     rax
0x18000a660  sbb     rcx, rcx
0x18000a663  and     rcx, rdx; punk
0x18000a666  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000a66d  call    cs:__imp_IUnknown_GetSite
0x18000a673  mov     ebx, eax
0x18000a675  test    eax, eax
0x18000a677  js      short loc_18000A6C3
0x18000a679  mov     rcx, [r14]; punk
0x18000a67c  lea     r9, [rsp+38h+ppvOut]; ppvOut
0x18000a681  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000a688  mov     [rsp+38h+ppvOut], 0
0x18000a691  lea     rdx, SID_STopLevelBrowser; guidService
0x18000a698  call    cs:__imp_IUnknown_QueryService
0x18000a69e  mov     ebx, eax
0x18000a6a0  test    eax, eax
0x18000a6a2  js      short loc_18000A6C3
0x18000a6a4  mov     rcx, [rsp+38h+ppvOut]; punk
0x18000a6a9  mov     rdx, rdi; phwnd
0x18000a6ac  call    cs:__imp_IUnknown_GetWindow
0x18000a6b2  mov     rcx, [rsp+38h+ppvOut]
0x18000a6b7  mov     rax, [rcx]
0x18000a6ba  mov     rax, [rax+10h]
0x18000a6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6ca  cmp     rcx, r15
0x18000a6cd  jz      short loc_18000A6ED
0x18000a6cf  test    byte ptr [rcx+1Ch], 20h
0x18000a6d3  jz      short loc_18000A6ED
0x18000a6d5  mov     rcx, [rcx+10h]
0x18000a6d9  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000a6e0  mov     edx, 59h ; 'Y'
0x18000a6e5  mov     r9d, ebx
0x18000a6e8  call    WPP_SF_d
0x18000a6ed  mov     rax, [rdi]
0x18000a6f0  mov     rbx, [rsp+38h+arg_8]
0x18000a6f5  mov     rsi, [rsp+38h+arg_10]
0x18000a6fa  add     rsp, 20h
0x18000a6fe  pop     r15
0x18000a700  pop     r14
0x18000a702  pop     rdi
0x18000a703  retn
```
