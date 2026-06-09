# CWerComReport::_GetFileByIndex(ulong,ulong *,ulong *,ushort * *,ushort * *)

- ea: `0x18000f7f8`
- end: `0x18000f9d5`
- name: `?_GetFileByIndex@CWerComReport@@QEAAJKPEAK0PEAPEAG1@Z`
- size: `477`
- prototype: `__int64 __fastcall(CWerComReport *this, unsigned int, unsigned int *, unsigned int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b570`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000e35c`
- `0x18000f7f8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f91e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f983`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f91e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f983`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f908`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f96d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f908`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f96d`
- `wer!WerpGetFileByIndex` at `0x18000f8b4`
- `wer!WerpGetFileByIndex` at `0x18000f8b4`

## pseudocode

```c
__int64 __fastcall CWerComReport::_GetFileByIndex(
        CWerComReport *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  int WerApiLock; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  OLECHAR *v13; // rcx
  unsigned __int16 *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  OLECHAR *v17; // rcx
  unsigned __int16 *v18; // rax
  unsigned int v20; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-24h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-20h] BYREF
  OLECHAR *v23; // [rsp+50h] [rbp-18h] BYREF
  __int64 v24; // [rsp+58h] [rbp-10h] BYREF

  v20 = 11;
  v21 = 0;
  psz = 0;
  v23 = 0;
  v24 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v24, this);
  if ( WerApiLock < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 64;
LABEL_5:
      WPP_SF_d(v11[2], v12, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  WerApiLock = WerpGetFileByIndex(*((_QWORD *)this + 4), a2, &v20, &v21, &psz, &v23, 0);
  if ( WerApiLock < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 65;
      goto LABEL_5;
    }
    goto LABEL_28;
  }
  if ( a3 )
    *a3 = v20;
  if ( a4 )
    *a4 = v21;
  if ( a5 )
  {
    SysFreeString(*a5);
    v13 = psz;
    *a5 = 0;
    if ( v13 )
    {
      v14 = SysAllocString(v13);
      *a5 = v14;
      if ( !v14 )
      {
        WerApiLock = -2147024882;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_28;
        v16 = 66;
LABEL_20:
        WPP_SF_(v15[2], v16, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
        goto LABEL_28;
      }
    }
  }
  if ( !a6 || (SysFreeString(*a6), v17 = v23, *a6 = 0, !v17) || (v18 = SysAllocString(v17), (*a6 = v18) != 0) )
  {
    WerApiLock = 0;
    goto LABEL_28;
  }
  WerApiLock = -2147024882;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = 67;
    goto LABEL_20;
  }
LABEL_28:
  if ( v24 )
    _InterlockedExchange((volatile __int32 *)(v24 + 48), 0);
  return (unsigned int)WerApiLock;
}

```

## disassembly

```asm
0x18000f7f8  push    rbp
0x18000f7fa  push    rbx
0x18000f7fb  push    rsi
0x18000f7fc  push    rdi
0x18000f7fd  push    r14
0x18000f7ff  push    r15
0x18000f801  mov     rbp, rsp
0x18000f804  sub     rsp, 68h
0x18000f808  mov     r15d, edx
0x18000f80b  mov     [rbp+var_28], 0Bh
0x18000f812  mov     rdx, rcx; struct CWerComReport *
0x18000f815  mov     [rbp+var_24], 0
0x18000f81c  mov     r14, rcx
0x18000f81f  mov     [rbp+psz], 0
0x18000f827  lea     rcx, [rbp+var_10]; this
0x18000f82b  mov     [rbp+var_18], 0
0x18000f833  mov     rdi, r9
0x18000f836  mov     [rbp+var_10], 0
0x18000f83e  mov     rsi, r8
0x18000f841  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18000f846  mov     ebx, eax
0x18000f848  test    eax, eax
0x18000f84a  jns     short loc_18000F88A
0x18000f84c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f853  lea     rax, WPP_GLOBAL_Control
0x18000f85a  cmp     rcx, rax
0x18000f85d  jz      loc_18000F9B8
0x18000f863  test    byte ptr [rcx+1Ch], 1
0x18000f867  jz      loc_18000F9B8
0x18000f86d  mov     edx, 40h ; '@'
0x18000f872  mov     rcx, [rcx+10h]
0x18000f876  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f87d  mov     r9d, ebx
0x18000f880  call    WPP_SF_d
0x18000f885  jmp     loc_18000F9B8
0x18000f88a  mov     rcx, [r14+20h]
0x18000f88e  lea     rax, [rbp+var_18]
0x18000f892  mov     [rsp+68h+var_38], 0
0x18000f89b  lea     r9, [rbp+var_24]
0x18000f89f  mov     [rsp+68h+var_40], rax
0x18000f8a4  lea     r8, [rbp+var_28]
0x18000f8a8  lea     rax, [rbp+psz]
0x18000f8ac  mov     edx, r15d
0x18000f8af  mov     [rsp+68h+var_48], rax
0x18000f8b4  call    cs:__imp_WerpGetFileByIndex
0x18000f8ba  mov     ebx, eax
0x18000f8bc  test    eax, eax
0x18000f8be  jns     short loc_18000F8E8
0x18000f8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8c7  lea     rax, WPP_GLOBAL_Control
0x18000f8ce  cmp     rcx, rax
0x18000f8d1  jz      loc_18000F9B8
0x18000f8d7  test    byte ptr [rcx+1Ch], 1
0x18000f8db  jz      loc_18000F9B8
0x18000f8e1  mov     edx, 41h ; 'A'
0x18000f8e6  jmp     short loc_18000F872
0x18000f8e8  test    rsi, rsi
0x18000f8eb  jz      short loc_18000F8F2
0x18000f8ed  mov     eax, [rbp+var_28]
0x18000f8f0  mov     [rsi], eax
0x18000f8f2  test    rdi, rdi
0x18000f8f5  jz      short loc_18000F8FC
0x18000f8f7  mov     eax, [rbp+var_24]
0x18000f8fa  mov     [rdi], eax
0x18000f8fc  mov     rbx, [rbp+arg_20]
0x18000f900  test    rbx, rbx
0x18000f903  jz      short loc_18000F961
0x18000f905  mov     rcx, [rbx]; bstrString
0x18000f908  call    cs:__imp_SysFreeString
0x18000f90e  mov     rcx, [rbp+psz]; psz
0x18000f912  mov     qword ptr [rbx], 0
0x18000f919  test    rcx, rcx
0x18000f91c  jz      short loc_18000F961
0x18000f91e  call    cs:__imp_SysAllocString
0x18000f924  mov     [rbx], rax
0x18000f927  test    rax, rax
0x18000f92a  jnz     short loc_18000F961
0x18000f92c  mov     ebx, 8007000Eh
0x18000f931  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f938  lea     rax, WPP_GLOBAL_Control
0x18000f93f  cmp     rcx, rax
0x18000f942  jz      short loc_18000F9B8
0x18000f944  test    byte ptr [rcx+1Ch], 1
0x18000f948  jz      short loc_18000F9B8
0x18000f94a  mov     edx, 42h ; 'B'
0x18000f94f  mov     rcx, [rcx+10h]
0x18000f953  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f95a  call    WPP_SF_
0x18000f95f  jmp     short loc_18000F9B8
0x18000f961  mov     rbx, [rbp+arg_28]
0x18000f965  test    rbx, rbx
0x18000f968  jz      short loc_18000F9B6
0x18000f96a  mov     rcx, [rbx]; bstrString
0x18000f96d  call    cs:__imp_SysFreeString
0x18000f973  mov     rcx, [rbp+var_18]; psz
0x18000f977  mov     qword ptr [rbx], 0
0x18000f97e  test    rcx, rcx
0x18000f981  jz      short loc_18000F9B6
0x18000f983  call    cs:__imp_SysAllocString
0x18000f989  mov     [rbx], rax
0x18000f98c  test    rax, rax
0x18000f98f  jnz     short loc_18000F9B6
0x18000f991  mov     ebx, 8007000Eh
0x18000f996  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f99d  lea     rax, WPP_GLOBAL_Control
0x18000f9a4  cmp     rcx, rax
0x18000f9a7  jz      short loc_18000F9B8
0x18000f9a9  test    byte ptr [rcx+1Ch], 1
0x18000f9ad  jz      short loc_18000F9B8
0x18000f9af  mov     edx, 43h ; 'C'
0x18000f9b4  jmp     short loc_18000F94F
0x18000f9b6  xor     ebx, ebx
0x18000f9b8  mov     rax, [rbp+var_10]
0x18000f9bc  test    rax, rax
0x18000f9bf  jz      short loc_18000F9C6
0x18000f9c1  xor     ecx, ecx
0x18000f9c3  xchg    ecx, [rax+30h]
0x18000f9c6  mov     eax, ebx
0x18000f9c8  add     rsp, 68h
0x18000f9cc  pop     r15
0x18000f9ce  pop     r14
0x18000f9d0  pop     rdi
0x18000f9d1  pop     rsi
0x18000f9d2  pop     rbx
0x18000f9d3  pop     rbp
0x18000f9d4  retn
```
