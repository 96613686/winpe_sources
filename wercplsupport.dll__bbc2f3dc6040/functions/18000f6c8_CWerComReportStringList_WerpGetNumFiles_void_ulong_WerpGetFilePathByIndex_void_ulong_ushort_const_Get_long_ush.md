# CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&WerpGetFilePathByIndex(void *,ulong,ushort const * *)>::_Get(long,ushort * *)

- ea: `0x18000f6c8`
- end: `0x18000f7ef`
- name: `?_Get@?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?WerpGetFilePathByIndex@@YAJ0KPEAPEBG@Z@@QEAAJJPEAPEAG@Z`
- size: `295`
- prototype: `__int64 __fastcall(__int64, unsigned int, BSTR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000afa0`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000e35c`
- `0x18000f6c8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f795`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f795`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f78a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f78a`
- `wer!WerpGetFilePathByIndex` at `0x18000f75b`
- `wer!WerpGetFilePathByIndex` at `0x18000f75b`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long WerpGetFilePathByIndex(void *,unsigned long,unsigned short const * *)>::_Get(
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
  WerApiLock = WerpGetFilePathByIndex(*(_QWORD *)(a1 + 32), a2, &psz);
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
0x18000f6c8  mov     rax, rsp
0x18000f6cb  mov     [rax+10h], rbx
0x18000f6cf  push    rbp
0x18000f6d0  push    rsi
0x18000f6d1  push    rdi
0x18000f6d2  sub     rsp, 20h
0x18000f6d6  mov     ebp, edx
0x18000f6d8  mov     qword ptr [rax+20h], 0
0x18000f6e0  mov     rdx, [rcx+28h]; struct CWerComReport *
0x18000f6e4  mov     rsi, rcx
0x18000f6e7  lea     rcx, [rax+8]; this
0x18000f6eb  mov     qword ptr [rax+8], 0
0x18000f6f3  mov     rdi, r8
0x18000f6f6  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18000f6fb  mov     ebx, eax
0x18000f6fd  test    eax, eax
0x18000f6ff  jns     short loc_18000F750
0x18000f701  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f708  lea     rdx, WPP_GLOBAL_Control
0x18000f70f  cmp     rcx, rdx
0x18000f712  jz      short loc_18000F732
0x18000f714  test    byte ptr [rcx+1Ch], 1
0x18000f718  jz      short loc_18000F732
0x18000f71a  mov     edx, 0Eh
0x18000f71f  mov     rcx, [rcx+10h]
0x18000f723  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f72a  mov     r9d, ebx
0x18000f72d  call    WPP_SF_d
0x18000f732  mov     rax, [rsp+38h+arg_0]
0x18000f737  test    rax, rax
0x18000f73a  jz      short loc_18000F741
0x18000f73c  xor     ecx, ecx
0x18000f73e  xchg    ecx, [rax+30h]
0x18000f741  mov     eax, ebx
0x18000f743  mov     rbx, [rsp+38h+arg_8]
0x18000f748  add     rsp, 20h
0x18000f74c  pop     rdi
0x18000f74d  pop     rsi
0x18000f74e  pop     rbp
0x18000f74f  retn
0x18000f750  mov     rcx, [rsi+20h]
0x18000f754  lea     r8, [rsp+38h+psz]
0x18000f759  mov     edx, ebp
0x18000f75b  call    cs:__imp_WerpGetFilePathByIndex
0x18000f761  mov     ebx, eax
0x18000f763  test    eax, eax
0x18000f765  jns     short loc_18000F787
0x18000f767  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f76e  lea     rdx, WPP_GLOBAL_Control
0x18000f775  cmp     rcx, rdx
0x18000f778  jz      short loc_18000F732
0x18000f77a  test    byte ptr [rcx+1Ch], 1
0x18000f77e  jz      short loc_18000F732
0x18000f780  mov     edx, 0Fh
0x18000f785  jmp     short loc_18000F71F
0x18000f787  mov     rcx, [rdi]; bstrString
0x18000f78a  call    cs:__imp_SysFreeString
0x18000f790  mov     rcx, [rsp+38h+psz]; psz
0x18000f795  call    cs:__imp_SysAllocString
0x18000f79b  mov     [rdi], rax
0x18000f79e  test    rax, rax
0x18000f7a1  jnz     short loc_18000F732
0x18000f7a3  cmp     [rsp+38h+psz], rax
0x18000f7a8  jz      short loc_18000F732
0x18000f7aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7b1  lea     rdx, WPP_GLOBAL_Control
0x18000f7b8  cmp     rcx, rdx
0x18000f7bb  jz      short loc_18000F7D6
0x18000f7bd  test    byte ptr [rcx+1Ch], 1
0x18000f7c1  jz      short loc_18000F7D6
0x18000f7c3  mov     rcx, [rcx+10h]
0x18000f7c7  lea     edx, [rax+10h]
0x18000f7ca  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f7d1  call    WPP_SF_
0x18000f7d6  mov     rax, [rsp+38h+arg_0]
0x18000f7db  test    rax, rax
0x18000f7de  jz      short loc_18000F7E5
0x18000f7e0  xor     ecx, ecx
0x18000f7e2  xchg    ecx, [rax+30h]
0x18000f7e5  mov     eax, 8007000Eh
0x18000f7ea  jmp     loc_18000F743
```
