# ConfigBase::DeleteRegValue(ushort const *)

- ea: `0x180015acc`
- end: `0x180015b7f`
- name: `?DeleteRegValue@ConfigBase@@IEAA_NPEBG@Z`
- size: `179`
- prototype: `char __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800165c0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180015acc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015ad6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015ad6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ConfigBase::DeleteRegValue(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v5; // [rsp+28h] [rbp-40h]
  const char *v6; // [rsp+30h] [rbp-38h]
  __int64 v7; // [rsp+38h] [rbp-30h]
  __int64 v8; // [rsp+40h] [rbp-28h]
  unsigned int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]
  int v11; // [rsp+50h] [rbp-18h]

  v2 = RegDeleteValueW(this[2], a2);
  if ( !v2 )
    return 1;
  if ( v2 != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v2);
    }
    v5 = 0;
    v6 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v8 = 0;
    v9 = v2;
    v10 = -1;
    v11 = 113;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x180015acc  push    rbx
0x180015ace  sub     rsp, 60h
0x180015ad2  mov     rcx, [rcx+10h]; hKey
0x180015ad6  call    cs:__imp_RegDeleteValueW
0x180015adc  mov     ebx, eax
0x180015ade  test    eax, eax
0x180015ae0  jnz     short loc_180015AEA
0x180015ae2  mov     al, 1
0x180015ae4  add     rsp, 60h
0x180015ae8  pop     rbx
0x180015ae9  retn
0x180015aea  cmp     ebx, 2
0x180015aed  jnz     short loc_180015AF3
0x180015aef  xor     al, al
0x180015af1  jmp     short loc_180015AE4
0x180015af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180015afa  lea     rax, WPP_GLOBAL_Control
0x180015b01  cmp     rcx, rax
0x180015b04  jz      short loc_180015B2A
0x180015b06  test    byte ptr [rcx+1Ch], 40h
0x180015b0a  jz      short loc_180015B2A
0x180015b0c  cmp     byte ptr [rcx+19h], 2
0x180015b10  jb      short loc_180015B2A
0x180015b12  mov     rcx, [rcx+10h]
0x180015b16  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180015b1d  mov     edx, 10h
0x180015b22  mov     r9d, ebx
0x180015b25  call    WPP_SF_D
0x180015b2a  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x180015b31  mov     [rsp+68h+var_40], 0
0x180015b36  mov     [rsp+68h+var_38], rax
0x180015b3b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180015b42  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180015b49  mov     [rsp+68h+var_30], 0
0x180015b52  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180015b57  mov     [rsp+68h+pExceptionObject], rax
0x180015b5c  mov     [rsp+68h+var_28], 0
0x180015b65  mov     [rsp+68h+var_20], ebx
0x180015b69  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x180015b71  mov     [rsp+68h+var_18], 71h ; 'q'
0x180015b79  call    _CxxThrowException_0
```
