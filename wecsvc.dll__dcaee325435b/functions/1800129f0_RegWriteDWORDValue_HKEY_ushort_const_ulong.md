# RegWriteDWORDValue(HKEY__ *,ushort const *,ulong)

- ea: `0x1800129f0`
- end: `0x180012ab9`
- name: `?RegWriteDWORDValue@@YAXPEAUHKEY__@@PEBGK@Z`
- size: `201`
- prototype: `void __fastcall(HKEY, const unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e2f8`
- `0x18000fd88`
- `0x1800103b8`
- `0x1800165c0`
- `0x1800178f0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x1800129f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012a18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012a18`

## string_xrefs

- `0x180012a5f`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegWriteDWORDValue(HKEY a1, const unsigned __int16 *a2, int a3)
{
  unsigned int v3; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char v5; // [rsp+38h] [rbp-38h]
  const char *v6; // [rsp+40h] [rbp-30h]
  __int64 v7; // [rsp+48h] [rbp-28h]
  __int64 v8; // [rsp+50h] [rbp-20h]
  unsigned int v9; // [rsp+58h] [rbp-18h]
  int v10; // [rsp+5Ch] [rbp-14h]
  int v11; // [rsp+60h] [rbp-10h]
  int v12; // [rsp+90h] [rbp+20h] BYREF

  v12 = a3;
  v3 = RegSetValueExW(a1, a2, 0, 4u, (const BYTE *)&v12, 4u);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v3);
    }
    v5 = 0;
    v6 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v8 = 0;
    v9 = v3;
    v10 = -1;
    v11 = 178;
    throw (wmi::GenericException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800129f0  mov     r11, rsp
0x1800129f3  mov     [r11+8], rbx
0x1800129f7  mov     [r11+18h], r8d
0x1800129fb  push    rbp
0x1800129fc  mov     rbp, rsp
0x1800129ff  sub     rsp, 70h
0x180012a03  mov     r9d, 4; dwType
0x180012a09  lea     rax, [rbp+arg_10]
0x180012a0d  mov     [r11-50h], r9d
0x180012a11  xor     r8d, r8d; Reserved
0x180012a14  mov     [r11-58h], rax
0x180012a18  call    cs:__imp_RegSetValueExW
0x180012a1e  mov     ebx, eax
0x180012a20  test    eax, eax
0x180012a22  jz      loc_180012AAB
0x180012a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a2f  lea     rax, WPP_GLOBAL_Control
0x180012a36  cmp     rcx, rax
0x180012a39  jz      short loc_180012A5F
0x180012a3b  test    byte ptr [rcx+1Ch], 1
0x180012a3f  jz      short loc_180012A5F
0x180012a41  cmp     byte ptr [rcx+19h], 2
0x180012a45  jb      short loc_180012A5F
0x180012a47  mov     rcx, [rcx+10h]
0x180012a4b  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180012a52  mov     edx, 12h
0x180012a57  mov     r9d, ebx
0x180012a5a  call    WPP_SF_D
0x180012a5f  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180012a66  mov     [rbp+var_38], 0
0x180012a6a  mov     [rbp+var_30], rax
0x180012a6e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012a75  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012a7c  mov     [rbp+var_28], 0
0x180012a84  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180012a88  mov     [rbp+pExceptionObject], rax
0x180012a8c  mov     [rbp+var_20], 0
0x180012a94  mov     [rbp+var_18], ebx
0x180012a97  mov     [rbp+var_14], 0FFFFFFFFh
0x180012a9e  mov     [rbp+var_10], 0B2h
0x180012aa5  call    _CxxThrowException_0
0x180012aab  mov     rbx, [rsp+70h+arg_0]
0x180012ab3  add     rsp, 70h
0x180012ab7  pop     rbp
0x180012ab8  retn
```
