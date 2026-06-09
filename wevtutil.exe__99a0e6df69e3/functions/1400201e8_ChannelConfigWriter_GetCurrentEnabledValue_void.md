# ChannelConfigWriter::GetCurrentEnabledValue(void)

- ea: `0x1400201e8`
- end: `0x1400202bc`
- name: `?GetCurrentEnabledValue@ChannelConfigWriter@@AEBA_NXZ`
- size: `212`
- prototype: `bool __fastcall(ChannelConfigWriter *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14001eb9c`
- `0x1400203a8`

## callees

- `0x140008870`
- `0x140019348`
- `0x1400201e8`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
bool __fastcall ChannelConfigWriter::GetCurrentEnabledValue(ChannelConfigWriter *this)
{
  __int64 v2; // rdx
  const wchar_t *v3; // rdx
  HKEY v5; // rcx
  unsigned int v6; // ebx
  const char *v7; // r8
  const wchar_t *v8[2]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v10; // [rsp+70h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 36);
  v8[0] = *((const wchar_t **)this + 35);
  v8[1] = (const wchar_t *)((signed __int64)(v2 - (unsigned __int64)v8[0]) >> 1);
  if ( IsCoreChannel(v8) )
    return 1;
  v5 = (HKEY)*((_QWORD *)this + 32);
  v10 = 0;
  v6 = RegReadDWORDValueNoThrow(v5, v3, L"Enabled", &v10);
  if ( v6 == 2 )
    return 0;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, v6);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v6, v7, 264);
    throw (EvtException *)pExceptionObject;
  }
  return v10 != 0;
}

```

## disassembly

```asm
0x1400201e8  push    rbx
0x1400201ea  sub     rsp, 60h
0x1400201ee  mov     rax, [rcx+118h]
0x1400201f5  mov     rbx, rcx
0x1400201f8  mov     rdx, [rcx+120h]
0x1400201ff  lea     rcx, [rsp+68h+var_48]
0x140020204  sub     rdx, rax
0x140020207  mov     [rsp+68h+var_48], rax
0x14002020c  sar     rdx, 1
0x14002020f  mov     [rsp+68h+var_40], rdx
0x140020214  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140020219  test    al, al
0x14002021b  jz      short loc_140020224
0x14002021d  mov     al, 1
0x14002021f  jmp     loc_1400202B6
0x140020224  mov     rcx, [rbx+100h]; HKEY
0x14002022b  lea     r9, [rsp+68h+arg_0]; unsigned int *
0x140020230  lea     r8, aEnabled; "Enabled"
0x140020237  mov     [rsp+68h+arg_0], 0
0x14002023f  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x140020244  mov     ebx, eax
0x140020246  cmp     eax, 2
0x140020249  jnz     short loc_14002024F
0x14002024b  xor     al, al
0x14002024d  jmp     short loc_1400202B6
0x14002024f  test    ebx, ebx
0x140020251  jz      short loc_1400202AE
0x140020253  mov     rcx, cs:WPP_GLOBAL_Control
0x14002025a  lea     rax, WPP_GLOBAL_Control
0x140020261  cmp     rcx, rax
0x140020264  jz      short loc_14002028A
0x140020266  test    byte ptr [rcx+1Ch], 4
0x14002026a  jz      short loc_14002028A
0x14002026c  cmp     byte ptr [rcx+19h], 2
0x140020270  jb      short loc_14002028A
0x140020272  mov     rcx, [rcx+10h]
0x140020276  lea     r8, WPP_dcf685af8c5436a5470889b599bac37f_Traceguids
0x14002027d  mov     edx, 17h
0x140020282  mov     r9d, ebx
0x140020285  call    WPP_SF_d
0x14002028a  mov     r9d, 108h; int
0x140020290  lea     rcx, [rsp+68h+pExceptionObject]; this
0x140020295  mov     edx, ebx; unsigned int
0x140020297  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002029c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400202a3  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1400202a8  call    _CxxThrowException_0
0x1400202ae  cmp     [rsp+68h+arg_0], 0
0x1400202b3  setnz   al
0x1400202b6  add     rsp, 60h
0x1400202ba  pop     rbx
0x1400202bb  retn
```
