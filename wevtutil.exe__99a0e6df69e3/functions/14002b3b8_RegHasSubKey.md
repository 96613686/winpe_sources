# RegHasSubKey

- ea: `0x14002b3b8`
- end: `0x14002b492`
- name: `RegHasSubKey`
- size: `218`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002a55c`
- `0x14002a814`

## callees

- `0x140006db0`
- `0x140022cec`
- `0x14002b3b8`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002b3ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002b3ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b409`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b47f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b409`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b47f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall RegHasSubKey(HKEY hKey, LPCWSTR lpSubKey)
{
  HKEY *phkResult; // rax
  unsigned int v5; // ebx
  const char *v6; // r8
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKeya; // [rsp+80h] [rbp+18h] BYREF

  hKeya = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKeya);
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, phkResult);
  if ( v5 == 2 )
  {
    if ( hKeya )
      RegCloseKey(hKeya);
    return 0;
  }
  else
  {
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, v5);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v5, v6, 110);
      throw (EvtException *)pExceptionObject;
    }
    if ( hKeya )
      RegCloseKey(hKeya);
    return 1;
  }
}

```

## disassembly

```asm
0x14002b3b8  mov     rax, rsp
0x14002b3bb  mov     [rax+8], rbx
0x14002b3bf  push    rdi
0x14002b3c0  sub     rsp, 60h
0x14002b3c4  mov     rbx, rdx
0x14002b3c7  mov     rdi, rcx
0x14002b3ca  mov     qword ptr [rax+18h], 0
0x14002b3d2  lea     rcx, [rax+18h]
0x14002b3d6  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002b3db  mov     [rsp+68h+phkResult], rax; phkResult
0x14002b3e0  mov     r9d, 20019h; samDesired
0x14002b3e6  xor     r8d, r8d; ulOptions
0x14002b3e9  mov     rdx, rbx; lpSubKey
0x14002b3ec  mov     rcx, rdi; hKey
0x14002b3ef  call    cs:__imp_RegOpenKeyExW
0x14002b3f5  mov     ebx, eax
0x14002b3f7  cmp     eax, 2
0x14002b3fa  jnz     short loc_14002B413
0x14002b3fc  mov     rcx, [rsp+68h+hKey]; hKey
0x14002b404  test    rcx, rcx
0x14002b407  jz      short loc_14002B40F
0x14002b409  call    cs:__imp_RegCloseKey
0x14002b40f  xor     al, al
0x14002b411  jmp     short loc_14002B487
0x14002b413  test    ebx, ebx
0x14002b415  jz      short loc_14002B472
0x14002b417  lea     rax, WPP_GLOBAL_Control
0x14002b41e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b425  cmp     rcx, rax
0x14002b428  jz      short loc_14002B44E
0x14002b42a  test    byte ptr [rcx+1Ch], 4
0x14002b42e  jz      short loc_14002B44E
0x14002b430  cmp     byte ptr [rcx+19h], 2
0x14002b434  jb      short loc_14002B44E
0x14002b436  mov     edx, 0Dh
0x14002b43b  mov     r9d, ebx
0x14002b43e  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14002b445  mov     rcx, [rcx+10h]
0x14002b449  call    WPP_SF_d
0x14002b44e  mov     r9d, 6Eh ; 'n'; int
0x14002b454  mov     edx, ebx; unsigned int
0x14002b456  lea     rcx, [rsp+68h+pExceptionObject]; this
0x14002b45b  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002b460  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002b467  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x14002b46c  call    _CxxThrowException_0
0x14002b472  mov     rcx, [rsp+68h+hKey]; hKey
0x14002b47a  test    rcx, rcx
0x14002b47d  jz      short loc_14002B485
0x14002b47f  call    cs:__imp_RegCloseKey
0x14002b485  mov     al, 1
0x14002b487  mov     rbx, [rsp+68h+arg_0]
0x14002b48c  add     rsp, 60h
0x14002b490  pop     rdi
0x14002b491  retn
```
