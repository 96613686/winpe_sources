# CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::_Get(long,ushort * *)

- ea: `0x18000f46c`
- end: `0x18000f593`
- name: `?_Get@?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@QEAAJJPEAPEAG@Z`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000aee0`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000e35c`
- `0x18000f46c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f539`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f539`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f52e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f52e`
- `wer!WerpGetUIParamByIndex` at `0x18000f4ff`
- `wer!WerpGetUIParamByIndex` at `0x18000f4ff`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::_Get(
        __int64 a1,
        unsigned int a2,
        BSTR *a3)
{
  struct CWerComReport *v4; // rdx
  int WerApiLock; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  BSTR v11; // rax
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp+20h] BYREF

  psz = 0;
  v4 = *(struct CWerComReport **)(a1 + 40);
  v12 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v12, v4);
  if ( WerApiLock < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 14;
LABEL_5:
      WPP_SF_d(v8[2], v9, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  WerApiLock = WerpGetUIParamByIndex(*(_QWORD *)(a1 + 32), a2, &psz);
  if ( WerApiLock < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 15;
      goto LABEL_5;
    }
LABEL_6:
    if ( v12 )
      _InterlockedExchange((volatile __int32 *)(v12 + 48), 0);
    return (unsigned int)WerApiLock;
  }
  SysFreeString(*a3);
  v11 = SysAllocString(psz);
  *a3 = v11;
  if ( v11 || !psz )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
  if ( v12 )
    _InterlockedExchange((volatile __int32 *)(v12 + 48), 0);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000f46c  mov     rax, rsp
0x18000f46f  mov     [rax+10h], rbx
0x18000f473  push    rbp
0x18000f474  push    rsi
0x18000f475  push    rdi
0x18000f476  sub     rsp, 20h
0x18000f47a  mov     ebp, edx
0x18000f47c  mov     qword ptr [rax+20h], 0
0x18000f484  mov     rdx, [rcx+28h]; struct CWerComReport *
0x18000f488  mov     rsi, rcx
0x18000f48b  lea     rcx, [rax+8]; this
0x18000f48f  mov     qword ptr [rax+8], 0
0x18000f497  mov     rdi, r8
0x18000f49a  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18000f49f  mov     ebx, eax
0x18000f4a1  test    eax, eax
0x18000f4a3  jns     short loc_18000F4F4
0x18000f4a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4ac  lea     rdx, WPP_GLOBAL_Control
0x18000f4b3  cmp     rcx, rdx
0x18000f4b6  jz      short loc_18000F4D6
0x18000f4b8  test    byte ptr [rcx+1Ch], 1
0x18000f4bc  jz      short loc_18000F4D6
0x18000f4be  mov     edx, 0Eh
0x18000f4c3  mov     rcx, [rcx+10h]
0x18000f4c7  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f4ce  mov     r9d, ebx
0x18000f4d1  call    WPP_SF_d
0x18000f4d6  mov     rax, [rsp+38h+arg_0]
0x18000f4db  test    rax, rax
0x18000f4de  jz      short loc_18000F4E5
0x18000f4e0  xor     ecx, ecx
0x18000f4e2  xchg    ecx, [rax+30h]
0x18000f4e5  mov     eax, ebx
0x18000f4e7  mov     rbx, [rsp+38h+arg_8]
0x18000f4ec  add     rsp, 20h
0x18000f4f0  pop     rdi
0x18000f4f1  pop     rsi
0x18000f4f2  pop     rbp
0x18000f4f3  retn
0x18000f4f4  mov     rcx, [rsi+20h]
0x18000f4f8  lea     r8, [rsp+38h+psz]
0x18000f4fd  mov     edx, ebp
0x18000f4ff  call    cs:__imp_WerpGetUIParamByIndex
0x18000f505  mov     ebx, eax
0x18000f507  test    eax, eax
0x18000f509  jns     short loc_18000F52B
0x18000f50b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f512  lea     rdx, WPP_GLOBAL_Control
0x18000f519  cmp     rcx, rdx
0x18000f51c  jz      short loc_18000F4D6
0x18000f51e  test    byte ptr [rcx+1Ch], 1
0x18000f522  jz      short loc_18000F4D6
0x18000f524  mov     edx, 0Fh
0x18000f529  jmp     short loc_18000F4C3
0x18000f52b  mov     rcx, [rdi]; bstrString
0x18000f52e  call    cs:__imp_SysFreeString
0x18000f534  mov     rcx, [rsp+38h+psz]; psz
0x18000f539  call    cs:__imp_SysAllocString
0x18000f53f  mov     [rdi], rax
0x18000f542  test    rax, rax
0x18000f545  jnz     short loc_18000F4D6
0x18000f547  cmp     [rsp+38h+psz], rax
0x18000f54c  jz      short loc_18000F4D6
0x18000f54e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f555  lea     rdx, WPP_GLOBAL_Control
0x18000f55c  cmp     rcx, rdx
0x18000f55f  jz      short loc_18000F57A
0x18000f561  test    byte ptr [rcx+1Ch], 1
0x18000f565  jz      short loc_18000F57A
0x18000f567  mov     rcx, [rcx+10h]
0x18000f56b  lea     edx, [rax+10h]
0x18000f56e  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f575  call    WPP_SF_
0x18000f57a  mov     rax, [rsp+38h+arg_0]
0x18000f57f  test    rax, rax
0x18000f582  jz      short loc_18000F589
0x18000f584  xor     ecx, ecx
0x18000f586  xchg    ecx, [rax+30h]
0x18000f589  mov     eax, 8007000Eh
0x18000f58e  jmp     loc_18000F4E7
```
