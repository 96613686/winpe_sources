# I_GenerateGuid(ushort *,ulong)

- ea: `0x180028250`
- end: `0x18002848c`
- name: `?I_GenerateGuid@@YAKPEAGK@Z`
- size: `572`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `7`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800085b8`
- `0x18000a81c`
- `0x180016954`
- `0x180023a38`
- `0x180023e54`
- `0x180024378`
- `0x180024aac`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x18000bc48`
- `0x18000c198`
- `0x180016040`
- `0x1800272c0`
- `0x1800278a0`
- `0x180027dfc`
- `0x180028250`
- `0x180029cb8`
- `0x1800348a0`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180028365`
- `RPCRT4!UuidToStringW` at `0x180028365`
- `RPCRT4!UuidCreate` at `0x180028303`
- `RPCRT4!UuidCreate` at `0x180028303`

## string_xrefs

- `0x18002834c`: `Unable to create GUID`
- `0x180028433`: `Unable to copy GUID string`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall I_GenerateGuid(unsigned __int16 *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rcx
  RPC_STATUS v5; // ebx
  _QWORD *v6; // rcx
  int v7; // edx
  const char *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // r9d
  RPC_STATUS v13; // [rsp+30h] [rbp-19h] BYREF
  int v14; // [rsp+34h] [rbp-15h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-11h] BYREF
  RPC_WSTR *p_StringUuid; // [rsp+40h] [rbp-9h] BYREF
  __int16 v17; // [rsp+48h] [rbp-1h]
  _QWORD *v18; // [rsp+50h] [rbp+7h] BYREF
  _QWORD v19[3]; // [rsp+58h] [rbp+Fh] BYREF
  UUID Uuid; // [rsp+70h] [rbp+27h] BYREF
  char v21[16]; // [rsp+80h] [rbp+37h] BYREF

  v13 = 0;
  v14 = 0;
  strcpy(v21, "I_GenerateGuid");
  v19[0] = v21;
  v19[1] = &v14;
  v19[2] = &v13;
  lambda_5c0ec6a2c47571c6236b41d3de3bcb67_::operator()(v19);
  v14 = 1;
  v18 = v19;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
  memset_0(a1, 0, 0x50u);
  Uuid = 0;
  v5 = UuidCreate(&Uuid);
  if ( v5 )
  {
    WppTraceIndent(v4, 2);
    v13 = v5;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 17;
      v8 = "Unable to create GUID";
LABEL_13:
      WPP_SF_sDs(
        v6[2],
        v7,
        (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
        (_DWORD)WPP_pszIndent,
        v5,
        (__int64)v8);
      v5 = v13;
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  StringUuid = 0;
  v5 = UuidToStringW(&Uuid, &StringUuid);
  if ( !v5 )
  {
    p_StringUuid = &StringUuid;
    v17 = 256;
    v5 = StringCbCopyW(a1, 0x50u, StringUuid);
    if ( v5 < 0 )
    {
      WppTraceIndent(v10, 2);
      v13 = v5;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      WPP_SF_sds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
        v11,
        v5,
        (__int64)"Unable to copy GUID string");
    }
    v5 = v13;
LABEL_20:
    wil::details::ScopeExitFnGuard__lambda_0f4f0d0001516b57bd4585ba42865225___::operator()(&p_StringUuid);
    goto LABEL_21;
  }
  WppTraceIndent(v9, 2);
  v13 = v5;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 18;
    v8 = "Unable to get GUID string";
    goto LABEL_13;
  }
LABEL_21:
  WppTraceUnwinder__lambda_5c0ec6a2c47571c6236b41d3de3bcb67____::_WppTraceUnwinder__lambda_5c0ec6a2c47571c6236b41d3de3bcb67____(&v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028250  mov     [rsp-8+arg_8], rbx
0x180028255  mov     [rsp-8+arg_10], rdi
0x18002825a  push    rbp
0x18002825b  lea     rbp, [rsp-57h]
0x180028260  sub     rsp, 0A0h
0x180028267  mov     rax, cs:__security_cookie
0x18002826e  xor     rax, rsp
0x180028271  mov     [rbp+57h+var_10], rax
0x180028275  mov     rdi, rcx
0x180028278  mov     [rbp+57h+var_70], 0
0x18002827f  mov     [rbp+57h+var_6C], 0
0x180028286  movsd   xmm0, qword ptr cs:aIGenerateguid; "I_GenerateGuid"
0x18002828e  movsd   qword ptr [rbp+57h+var_20], xmm0
0x180028293  mov     eax, dword ptr cs:aIGenerateguid+8; "teGuid"
0x180028299  mov     dword ptr [rbp+57h+var_20+8], eax
0x18002829c  movzx   eax, word ptr cs:aIGenerateguid+0Ch; "id"
0x1800282a3  mov     word ptr [rbp+57h+var_20+0Ch], ax
0x1800282a7  mov     al, byte ptr cs:aIGenerateguid+0Eh; ""
0x1800282ad  mov     [rbp+57h+var_20+0Eh], al
0x1800282b0  lea     rax, [rbp+57h+var_20]
0x1800282b4  mov     [rbp+57h+var_48], rax
0x1800282b8  lea     rax, [rbp+57h+var_6C]
0x1800282bc  mov     [rbp+57h+var_40], rax
0x1800282c0  lea     rax, [rbp+57h+var_70]
0x1800282c4  mov     [rbp+57h+var_38], rax
0x1800282c8  lea     rcx, [rbp+57h+var_48]
0x1800282cc  call    _lambda_5c0ec6a2c47571c6236b41d3de3bcb67___operator__
0x1800282d1  mov     [rbp+57h+var_6C], 1
0x1800282d8  lea     rax, [rbp+57h+var_48]
0x1800282dc  mov     [rbp+57h+var_50], rax
0x1800282e0  test    rdi, rdi
0x1800282e3  jnz     short loc_1800282EA
0x1800282e5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800282ea  xor     edx, edx; Val
0x1800282ec  lea     r8d, [rdx+50h]; Size
0x1800282f0  mov     rcx, rdi; void *
0x1800282f3  call    memset_0
0x1800282f8  xorps   xmm0, xmm0
0x1800282fb  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800282ff  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180028303  call    cs:__imp_UuidCreate
0x180028309  mov     ebx, eax
0x18002830b  test    eax, eax
0x18002830d  jz      short loc_180028355
0x18002830f  mov     edx, 2
0x180028314  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180028319  mov     [rbp+57h+var_70], ebx
0x18002831c  lea     rax, WPP_GLOBAL_Control
0x180028323  mov     rcx, cs:WPP_GLOBAL_Control
0x18002832a  cmp     rcx, rax
0x18002832d  jz      loc_180028460
0x180028333  test    byte ptr [rcx+1Ch], 1
0x180028337  jz      loc_180028460
0x18002833d  cmp     byte ptr [rcx+19h], 2
0x180028341  jb      loc_180028460
0x180028347  mov     edx, 11h
0x18002834c  lea     rax, aUnableToCreate_9; "Unable to create GUID"
0x180028353  jmp     short loc_1800283B5
0x180028355  mov     [rbp+57h+StringUuid], 0
0x18002835d  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x180028361  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180028365  call    cs:__imp_UuidToStringW
0x18002836b  mov     ebx, eax
0x18002836d  test    eax, eax
0x18002836f  jz      short loc_1800283DD
0x180028371  mov     edx, 2
0x180028376  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002837b  mov     [rbp+57h+var_70], ebx
0x18002837e  lea     rax, WPP_GLOBAL_Control
0x180028385  mov     rcx, cs:WPP_GLOBAL_Control
0x18002838c  cmp     rcx, rax
0x18002838f  jz      loc_180028460
0x180028395  test    byte ptr [rcx+1Ch], 1
0x180028399  jz      loc_180028460
0x18002839f  cmp     byte ptr [rcx+19h], 2
0x1800283a3  jb      loc_180028460
0x1800283a9  mov     edx, 12h
0x1800283ae  lea     rax, aUnableToGetGui; "Unable to get GUID string"
0x1800283b5  mov     [rsp+0A0h+var_78], rax
0x1800283ba  mov     [rsp+0A0h+var_80], ebx
0x1800283be  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800283c5  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x1800283cc  mov     rcx, [rcx+10h]
0x1800283d0  call    WPP_SF_sDs
0x1800283d5  mov     ebx, [rbp+57h+var_70]
0x1800283d8  jmp     loc_180028460
0x1800283dd  lea     rax, [rbp+57h+StringUuid]
0x1800283e1  mov     [rbp+57h+var_60], rax
0x1800283e5  mov     [rbp+57h+var_58], 100h
0x1800283eb  mov     r8, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800283ef  mov     edx, 50h ; 'P'; unsigned __int64
0x1800283f4  mov     rcx, rdi; unsigned __int16 *
0x1800283f7  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800283fc  mov     ebx, eax
0x1800283fe  test    eax, eax
0x180028400  jns     short loc_180028453
0x180028402  mov     edx, 2
0x180028407  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002840c  mov     [rbp+57h+var_70], ebx
0x18002840f  lea     rax, WPP_GLOBAL_Control
0x180028416  mov     rcx, cs:WPP_GLOBAL_Control
0x18002841d  cmp     rcx, rax
0x180028420  jz      short loc_180028456
0x180028422  test    byte ptr [rcx+1Ch], 1
0x180028426  jz      short loc_180028456
0x180028428  cmp     byte ptr [rcx+19h], 2
0x18002842c  jb      short loc_180028456
0x18002842e  mov     edx, 13h
0x180028433  lea     rax, aUnableToCopyGu; "Unable to copy GUID string"
0x18002843a  mov     [rsp+0A0h+var_78], rax
0x18002843f  mov     [rsp+0A0h+var_80], ebx
0x180028443  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x18002844a  mov     rcx, [rcx+10h]
0x18002844e  call    WPP_SF_sds
0x180028453  mov     ebx, [rbp+57h+var_70]
0x180028456  lea     rcx, [rbp+57h+var_60]
0x18002845a  call    wil__details__ScopeExitFnGuard__lambda_0f4f0d0001516b57bd4585ba42865225_____operator__
0x18002845f  nop
0x180028460  lea     rcx, [rbp+57h+var_50]
0x180028464  call    WppTraceUnwinder__lambda_5c0ec6a2c47571c6236b41d3de3bcb67_______WppTraceUnwinder__lambda_5c0ec6a2c47571c6236b41d3de3bcb67____
0x180028469  mov     eax, ebx
0x18002846b  mov     rcx, [rbp+57h+var_10]
0x18002846f  xor     rcx, rsp; StackCookie
0x180028472  call    __security_check_cookie
0x180028477  lea     r11, [rsp+0A0h+var_s0]
0x18002847f  mov     rbx, [r11+18h]
0x180028483  mov     rdi, [r11+20h]
0x180028487  mov     rsp, r11
0x18002848a  pop     rbp
0x18002848b  retn
```
