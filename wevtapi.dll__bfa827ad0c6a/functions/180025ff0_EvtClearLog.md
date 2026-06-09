# EvtClearLog

- ea: `0x180025ff0`
- end: `0x18002619c`
- name: `EvtClearLog`
- size: `428`
- prototype: `BOOL __stdcall(EVT_HANDLE Session, LPCWSTR ChannelPath, LPCWSTR TargetFilePath, DWORD Flags)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002683c`

## callees

- `0x180006aec`
- `0x180007940`
- `0x180007aa0`
- `0x18000a724`
- `0x18000c404`
- `0x180013f6c`
- `0x180014bb0`
- `0x180023548`
- `0x180025ff0`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026176`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026176`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __stdcall EvtClearLog(EVT_HANDLE Session, LPCWSTR ChannelPath, LPCWSTR TargetFilePath, DWORD Flags)
{
  BOOL v7; // ebx
  const wchar_t *v8; // rdi
  DWORD v9; // edi
  struct Session *v11; // [rsp+20h] [rbp-98h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-90h] BYREF
  __int64 v13; // [rsp+38h] [rbp-80h]
  int v14; // [rsp+40h] [rbp-78h]
  int v15; // [rsp+44h] [rbp-74h]
  int v16; // [rsp+48h] [rbp-70h]
  __int128 v17; // [rsp+50h] [rbp-68h] BYREF
  __int64 v18; // [rsp+60h] [rbp-58h]
  int v19; // [rsp+68h] [rbp-50h]
  int v20; // [rsp+6Ch] [rbp-4Ch]
  int v21; // [rsp+70h] [rbp-48h]
  EvtException *v22; // [rsp+78h] [rbp-40h] BYREF
  wchar_t *v23[4]; // [rsp+80h] [rbp-38h] BYREF

  LastErrInfo::Reset((LastErrInfo *)Session);
  try
  {
    v7 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v13 = 0;
      v14 = 87;
      v15 = -1;
      v16 = 1157;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !ChannelPath )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      v17 = 0;
      v18 = 0;
      v19 = 87;
      v20 = -1;
      v21 = 1162;
      throw (EvtException *)&v17;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v23);
    if ( TargetFilePath )
    {
      FullyQualifyFilePath((__int64)v23, TargetFilePath);
      v8 = v23[0];
    }
    else
    {
      v8 = 0;
    }
    GetSession(&v11);
    LogHandle::ClearLog(v11, ChannelPath, v8, 0);
    v9 = 0;
    wmi::AutoRef<Object>::Release(&v11);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v23);
  }
  catch ( EvtException *v22 )
  {
    v7 = 0;
    v9 = *((_DWORD *)v22 + 6);
  }
  SetLastError(v9);
  LOBYTE(v7) = v9 == 0;
  return v7;
}

```

## disassembly

```asm
0x180025ff0  mov     [rsp+arg_0], rbx
0x180025ff5  mov     [rsp+arg_8], rsi
0x180025ffa  push    rdi
0x180025ffb  push    r14
0x180025ffd  push    r15
0x180025fff  sub     rsp, 0A0h
0x180026006  mov     r14d, r9d
0x180026009  mov     rdi, r8
0x18002600c  mov     rsi, rdx
0x18002600f  mov     r15, rcx
0x180026012  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x180026017  xor     ebx, ebx
0x180026019  test    r14d, r14d
0x18002601c  jz      short loc_18002608B
0x18002601e  lea     rax, WPP_GLOBAL_Control
0x180026025  mov     rcx, cs:WPP_GLOBAL_Control
0x18002602c  cmp     rcx, rax
0x18002602f  jz      short loc_180026054
0x180026031  test    byte ptr [rcx+1Ch], 1
0x180026035  jz      short loc_180026054
0x180026037  cmp     byte ptr [rcx+19h], 2
0x18002603b  jb      short loc_180026054
0x18002603d  lea     edx, [rbx+22h]
0x180026040  lea     r9d, [rbx+57h]
0x180026044  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18002604b  mov     rcx, [rcx+10h]
0x18002604f  call    WPP_SF_D
0x180026054  xorps   xmm0, xmm0
0x180026057  movdqu  [rsp+0B8h+pExceptionObject], xmm0
0x18002605d  mov     [rsp+0B8h+var_80], rbx
0x180026062  mov     [rsp+0B8h+var_78], 57h ; 'W'
0x18002606a  mov     [rsp+0B8h+var_74], 0FFFFFFFFh
0x180026072  mov     [rsp+0B8h+var_70], 485h
0x18002607a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026081  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180026086  call    _CxxThrowException_0
0x18002608b  test    rsi, rsi
0x18002608e  jnz     short loc_1800260FD
0x180026090  lea     rax, WPP_GLOBAL_Control
0x180026097  mov     rcx, cs:WPP_GLOBAL_Control
0x18002609e  cmp     rcx, rax
0x1800260a1  jz      short loc_1800260C6
0x1800260a3  test    byte ptr [rcx+1Ch], 1
0x1800260a7  jz      short loc_1800260C6
0x1800260a9  cmp     byte ptr [rcx+19h], 2
0x1800260ad  jb      short loc_1800260C6
0x1800260af  lea     edx, [rsi+23h]
0x1800260b2  lea     r9d, [rsi+57h]
0x1800260b6  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800260bd  mov     rcx, [rcx+10h]
0x1800260c1  call    WPP_SF_D
0x1800260c6  xorps   xmm0, xmm0
0x1800260c9  movdqu  [rsp+0B8h+var_68], xmm0
0x1800260cf  mov     [rsp+0B8h+var_58], rbx
0x1800260d4  mov     [rsp+0B8h+var_50], 57h ; 'W'
0x1800260dc  mov     [rsp+0B8h+var_4C], 0FFFFFFFFh
0x1800260e4  mov     [rsp+0B8h+var_48], 48Ah
0x1800260ec  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800260f3  lea     rcx, [rsp+0B8h+var_68]; pExceptionObject
0x1800260f8  call    _CxxThrowException_0
0x1800260fd  lea     rcx, [rsp+0B8h+var_38]
0x180026105  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002610a  nop
0x18002610b  test    rdi, rdi
0x18002610e  jz      short loc_18002612A
0x180026110  mov     rdx, rdi
0x180026113  lea     rcx, [rsp+0B8h+var_38]
0x18002611b  call    FullyQualifyFilePath
0x180026120  mov     rdi, [rsp+0B8h+var_38]
0x180026128  jmp     short loc_18002612D
0x18002612a  mov     rdi, rbx
0x18002612d  mov     rdx, r15
0x180026130  lea     rcx, [rsp+0B8h+var_98]; void *
0x180026135  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18002613a  nop
0x18002613b  xor     r9d, r9d; unsigned int
0x18002613e  mov     r8, rdi; wchar_t *
0x180026141  mov     rdx, rsi; wchar_t *
0x180026144  mov     rcx, [rsp+0B8h+var_98]; this
0x180026149  call    ?ClearLog@LogHandle@@SAXPEAVSession@@PEB_W1K@Z; LogHandle::ClearLog(Session *,wchar_t const *,wchar_t const *,ulong)
0x18002614e  mov     edi, ebx
0x180026150  lea     rcx, [rsp+0B8h+var_98]; void *
0x180026155  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x18002615a  nop
0x18002615b  lea     rcx, [rsp+0B8h+var_38]
0x180026163  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180026168  nop
0x180026169  jmp     short loc_180026174
0x18002616b  xor     ebx, ebx
0x18002616d  mov     edi, [rsp+0B8h+arg_18]
0x180026174  mov     ecx, edi; dwErrCode
0x180026176  call    cs:__imp_SetLastError
0x18002617c  test    edi, edi
0x18002617e  setz    bl
0x180026181  mov     eax, ebx
0x180026183  lea     r11, [rsp+0B8h+var_18]
0x18002618b  mov     rbx, [r11+20h]
0x18002618f  mov     rsi, [r11+28h]
0x180026193  mov     rsp, r11
0x180026196  pop     r15
0x180026198  pop     r14
0x18002619a  pop     rdi
0x18002619b  retn
```
