# RegistryKeyEnumerator::Reset(HKEY__ *,wchar_t const *,void *)

- ea: `0x140018f58`
- end: `0x14001908d`
- name: `?Reset@RegistryKeyEnumerator@@QEAAJPEAUHKEY__@@PEB_WPEAX@Z`
- size: `309`
- prototype: `int(RegistryKeyEnumerator *__hidden this, HKEY, const wchar_t *, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140006a30`
- `0x140018e80`

## callees

- `0x140006db0`
- `0x140018f58`
- `0x14002ba08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018fa3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018fa3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14001903b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14001903b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140018f96`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140018f96`

## pseudocode

```c
__int64 __fastcall RegistryKeyEnumerator::Reset(DWORD *this, HKEY a2, const wchar_t *a3, void *a4)
{
  HKEY *phkResult; // rax
  LSTATUS v9; // eax
  unsigned int InfoKeyW; // ebx
  _QWORD *v11; // rcx
  int v12; // edx
  HKEY v13; // rcx

  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(this);
  if ( a4 == (void *)-1LL )
    v9 = RegOpenKeyExW(a2, a3, 0, 0x20019u, phkResult);
  else
    v9 = RegOpenKeyTransactedW(a2, a3, 0, 0x20019u, phkResult, a4, 0);
  InfoKeyW = v9;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 11;
LABEL_14:
      WPP_SF_SD(v11[2], v12, (unsigned int)WPP_50ea671b4016364e45441d7df5fd8e94_Traceguids, (_DWORD)a3, InfoKeyW);
    }
  }
  else
  {
    v13 = *(HKEY *)this;
    *((_QWORD *)this + 1) = a4;
    InfoKeyW = RegQueryInfoKeyW(v13, 0, 0, 0, this + 9, 0, 0, 0, 0, 0, 0, 0);
    if ( InfoKeyW )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 12;
        goto LABEL_14;
      }
    }
  }
  return InfoKeyW;
}

```

## disassembly

```asm
0x140018f58  push    rbx
0x140018f5a  push    rbp
0x140018f5b  push    rsi
0x140018f5c  push    rdi
0x140018f5d  sub     rsp, 68h
0x140018f61  mov     rbp, r9
0x140018f64  mov     rdi, r8
0x140018f67  mov     rbx, rdx
0x140018f6a  mov     rsi, rcx
0x140018f6d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140018f72  xor     r8d, r8d; ulOptions
0x140018f75  mov     r9d, 20019h; samDesired
0x140018f7b  mov     rdx, rdi; lpSubKey
0x140018f7e  mov     rcx, rbx; hKey
0x140018f81  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x140018f85  jz      short loc_140018F9E
0x140018f87  mov     [rsp+88h+pExtendedParemeter], r8; pExtendedParemeter
0x140018f8c  mov     [rsp+88h+hTransaction], rbp; hTransaction
0x140018f91  mov     [rsp+88h+phkResult], rax; phkResult
0x140018f96  call    cs:__imp_RegOpenKeyTransactedW
0x140018f9c  jmp     short loc_140018FA9
0x140018f9e  mov     [rsp+88h+phkResult], rax; phkResult
0x140018fa3  call    cs:__imp_RegOpenKeyExW
0x140018fa9  mov     ebx, eax
0x140018fab  test    eax, eax
0x140018fad  jz      short loc_140018FE4
0x140018faf  mov     rcx, cs:WPP_GLOBAL_Control
0x140018fb6  lea     rax, WPP_GLOBAL_Control
0x140018fbd  cmp     rcx, rax
0x140018fc0  jz      loc_140019082
0x140018fc6  test    byte ptr [rcx+1Ch], 4
0x140018fca  jz      loc_140019082
0x140018fd0  cmp     byte ptr [rcx+19h], 2
0x140018fd4  jb      loc_140019082
0x140018fda  mov     edx, 0Bh
0x140018fdf  jmp     loc_14001906B
0x140018fe4  mov     rcx, [rsi]; hKey
0x140018fe7  lea     rax, [rsi+24h]
0x140018feb  mov     [rsp+88h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140018ff4  xor     r9d, r9d; lpReserved
0x140018ff7  mov     [rsp+88h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x140019000  xor     r8d, r8d; lpcchClass
0x140019003  mov     [rsp+88h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x14001900c  xor     edx, edx; lpClass
0x14001900e  mov     [rsp+88h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x140019017  mov     [rsp+88h+lpcValues], 0; lpcValues
0x140019020  mov     [rsp+88h+pExtendedParemeter], 0; lpcbMaxClassLen
0x140019029  mov     [rsp+88h+hTransaction], 0; lpcbMaxSubKeyLen
0x140019032  mov     [rsp+88h+phkResult], rax; lpcSubKeys
0x140019037  mov     [rsi+8], rbp
0x14001903b  call    cs:__imp_RegQueryInfoKeyW
0x140019041  mov     ebx, eax
0x140019043  test    eax, eax
0x140019045  jz      short loc_140019082
0x140019047  mov     rcx, cs:WPP_GLOBAL_Control
0x14001904e  lea     rax, WPP_GLOBAL_Control
0x140019055  cmp     rcx, rax
0x140019058  jz      short loc_140019082
0x14001905a  test    byte ptr [rcx+1Ch], 4
0x14001905e  jz      short loc_140019082
0x140019060  cmp     byte ptr [rcx+19h], 2
0x140019064  jb      short loc_140019082
0x140019066  mov     edx, 0Ch
0x14001906b  mov     rcx, [rcx+10h]
0x14001906f  lea     r8, WPP_50ea671b4016364e45441d7df5fd8e94_Traceguids
0x140019076  mov     r9, rdi
0x140019079  mov     dword ptr [rsp+88h+phkResult], ebx
0x14001907d  call    WPP_SF_SD
0x140019082  mov     eax, ebx
0x140019084  add     rsp, 68h
0x140019088  pop     rdi
0x140019089  pop     rsi
0x14001908a  pop     rbp
0x14001908b  pop     rbx
0x14001908c  retn
```
