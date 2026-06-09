# IsMachineConnectedToInternet(bool *)

- ea: `0x180081bd8`
- end: `0x180081daa`
- name: `?IsMachineConnectedToInternet@@YAJPEA_N@Z`
- size: `466`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006c280`
- `0x18008fb88`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18002f808`
- `0x180081bd8`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180081c4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180081c4e`

## string_xrefs

- `0x180081c8b`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`

## pseudocode

```c
__int64 __fastcall IsMachineConnectedToInternet(bool *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  PVOID *v5; // rcx
  int v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int16 v9; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids);
  }
  ppv = 0;
  v9 = 0;
  *a1 = 0;
  v2 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &ppv);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 88LL))(ppv, &v9);
    v3 = v6;
    if ( v6 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        WPP_648969bf7a6635c96a81885b185e83e0_Traceguids,
        (unsigned int)v6);
    }
    *a1 = v9 == -1;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids, (unsigned int)v2);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x128,
    (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
    (const char *)v3);
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids, v3);
LABEL_19:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    ppv = 0;
  }
  if ( v5 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v5 + 28) & 0x20) != 0 && *((_BYTE *)v5 + 25) >= 5u )
    {
      LOBYTE(v4) = *a1;
      WPP_SF_c(v5[2], 58, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids, v4);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      WPP_SF_d(v5[2], 59, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180081bd8  mov     [rsp+arg_10], rbx
0x180081bdd  push    rbp
0x180081bde  push    rsi
0x180081bdf  push    rdi
0x180081be0  sub     rsp, 30h
0x180081be4  mov     rdi, rcx
0x180081be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180081bee  lea     rsi, WPP_GLOBAL_Control
0x180081bf5  lea     rbp, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids
0x180081bfc  cmp     rcx, rsi
0x180081bff  jz      short loc_180081C1E
0x180081c01  test    byte ptr [rcx+1Ch], 20h
0x180081c05  jz      short loc_180081C1E
0x180081c07  cmp     byte ptr [rcx+19h], 6
0x180081c0b  jb      short loc_180081C1E
0x180081c0d  mov     rcx, [rcx+10h]
0x180081c11  mov     edx, 36h ; '6'
0x180081c16  mov     r8, rbp
0x180081c19  call    WPP_SF_
0x180081c1e  xor     eax, eax
0x180081c20  mov     [rsp+48h+arg_8], 0
0x180081c29  xor     edx, edx; pUnkOuter
0x180081c2b  mov     [rsp+48h+arg_0], ax
0x180081c30  mov     [rdi], al
0x180081c32  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x180081c39  lea     rax, [rsp+48h+arg_8]
0x180081c3e  lea     rcx, CLSID_NetworkListManager; rclsid
0x180081c45  mov     [rsp+48h+ppv], rax; int
0x180081c4a  lea     r8d, [rdx+1]; dwClsContext
0x180081c4e  call    cs:__imp_CoCreateInstance
0x180081c54  mov     ebx, eax
0x180081c56  test    eax, eax
0x180081c58  jns     short loc_180081CC7
0x180081c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180081c61  cmp     rcx, rsi
0x180081c64  jz      short loc_180081C86
0x180081c66  test    byte ptr [rcx+1Ch], 8
0x180081c6a  jz      short loc_180081C86
0x180081c6c  cmp     byte ptr [rcx+19h], 2
0x180081c70  jb      short loc_180081C86
0x180081c72  mov     rcx, [rcx+10h]
0x180081c76  mov     edx, 37h ; '7'
0x180081c7b  mov     r9d, eax
0x180081c7e  mov     r8, rbp
0x180081c81  call    WPP_SF_d
0x180081c86  mov     rcx, [rsp+48h]; this
0x180081c8b  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180081c92  mov     r9d, ebx; char *
0x180081c95  mov     edx, 128h; void *
0x180081c9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180081c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180081ca6  cmp     rcx, rsi
0x180081ca9  jz      short loc_180081D21
0x180081cab  test    byte ptr [rcx+1Ch], 80h
0x180081caf  jz      short loc_180081D21
0x180081cb1  mov     rcx, [rcx+10h]
0x180081cb5  mov     edx, 38h ; '8'
0x180081cba  mov     r9d, ebx
0x180081cbd  mov     r8, rbp
0x180081cc0  call    WPP_SF_d
0x180081cc5  jmp     short loc_180081D1A
0x180081cc7  mov     rcx, [rsp+48h+arg_8]
0x180081ccc  lea     rdx, [rsp+48h+arg_0]
0x180081cd1  mov     rax, [rcx]
0x180081cd4  mov     rax, [rax+58h]
0x180081cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081cdd  mov     ebx, eax
0x180081cdf  test    eax, eax
0x180081ce1  jns     short loc_180081D0F
0x180081ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180081cea  cmp     rcx, rsi
0x180081ced  jz      short loc_180081D0F
0x180081cef  test    byte ptr [rcx+1Ch], 8
0x180081cf3  jz      short loc_180081D0F
0x180081cf5  cmp     byte ptr [rcx+19h], 2
0x180081cf9  jb      short loc_180081D0F
0x180081cfb  mov     rcx, [rcx+10h]
0x180081cff  mov     edx, 39h ; '9'
0x180081d04  mov     r9d, eax
0x180081d07  mov     r8, rbp
0x180081d0a  call    WPP_SF_d
0x180081d0f  cmp     [rsp+48h+arg_0], 0FFFFh
0x180081d15  setz    al
0x180081d18  mov     [rdi], al
0x180081d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180081d21  mov     rdx, [rsp+48h+arg_8]
0x180081d26  test    rdx, rdx
0x180081d29  jz      short loc_180081D4A
0x180081d2b  mov     rax, [rdx]
0x180081d2e  mov     rcx, rdx
0x180081d31  mov     rax, [rax+10h]
0x180081d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180081d41  mov     [rsp+48h+arg_8], 0
0x180081d4a  cmp     rcx, rsi
0x180081d4d  jz      short loc_180081D9B
0x180081d4f  test    byte ptr [rcx+1Ch], 20h
0x180081d53  jz      short loc_180081D76
0x180081d55  cmp     byte ptr [rcx+19h], 5
0x180081d59  jb      short loc_180081D76
0x180081d5b  mov     r9b, [rdi]
0x180081d5e  mov     edx, 3Ah ; ':'
0x180081d63  mov     rcx, [rcx+10h]
0x180081d67  mov     r8, rbp
0x180081d6a  call    WPP_SF_c
0x180081d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180081d76  cmp     rcx, rsi
0x180081d79  jz      short loc_180081D9B
0x180081d7b  test    byte ptr [rcx+1Ch], 20h
0x180081d7f  jz      short loc_180081D9B
0x180081d81  cmp     byte ptr [rcx+19h], 6
0x180081d85  jb      short loc_180081D9B
0x180081d87  mov     rcx, [rcx+10h]
0x180081d8b  mov     edx, 3Bh ; ';'
0x180081d90  mov     r9d, ebx
0x180081d93  mov     r8, rbp
0x180081d96  call    WPP_SF_d
0x180081d9b  mov     eax, ebx
0x180081d9d  mov     rbx, [rsp+48h+arg_10]
0x180081da2  add     rsp, 30h
0x180081da6  pop     rdi
0x180081da7  pop     rsi
0x180081da8  pop     rbp
0x180081da9  retn
```
