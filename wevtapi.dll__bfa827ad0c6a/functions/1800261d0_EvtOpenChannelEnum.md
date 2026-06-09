# EvtOpenChannelEnum

- ea: `0x1800261d0`
- end: `0x1800263ba`
- name: `EvtOpenChannelEnum`
- size: `490`
- prototype: `EVT_HANDLE __stdcall(EVT_HANDLE Session, DWORD Flags)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callees

- `0x180006aec`
- `0x180007010`
- `0x180007940`
- `0x180007aa0`
- `0x18001a71c`
- `0x180023548`
- `0x180023b1c`
- `0x18002590c`
- `0x1800261d0`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026383`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026383`
- `RPCRT4!NdrClientCall3` at `0x1800262d2`
- `RPCRT4!NdrClientCall3` at `0x1800262d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
EVT_HANDLE __stdcall EvtOpenChannelEnum(EVT_HANDLE Session, DWORD Flags)
{
  DWORD Pointer; // ebx
  __int64 v4; // rcx
  void *v5; // rbx
  __int64 v7; // [rsp+40h] [rbp-68h] BYREF
  __int64 v8; // [rsp+48h] [rbp-60h] BYREF
  int v9; // [rsp+54h] [rbp-54h]
  __int64 v10; // [rsp+58h] [rbp-50h] BYREF
  DWORD v11; // [rsp+60h] [rbp-48h]
  int v12; // [rsp+64h] [rbp-44h]
  char v13; // [rsp+68h] [rbp-40h]
  __int128 pExceptionObject; // [rsp+70h] [rbp-38h] BYREF
  __int64 v15; // [rsp+80h] [rbp-28h]
  int v16; // [rsp+88h] [rbp-20h]
  int v17; // [rsp+8Ch] [rbp-1Ch]
  int v18; // [rsp+90h] [rbp-18h]
  EvtException *v19; // [rsp+98h] [rbp-10h] BYREF
  DWORD v20; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+20h] BYREF

  v22 = 0;
  LastErrInfo::Reset((LastErrInfo *)Session);
  try
  {
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v15 = 0;
      v16 = 87;
      v17 = -1;
      v18 = 1345;
      throw (EvtException *)&pExceptionObject;
    }
    GetSession(&v8);
    v21 = 0;
    v20 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x13u,
                              0,
                              *(_QWORD *)(v8 + 72),
                              0,
                              &v20,
                              &v21).Pointer;
    v10 = v21;
    v11 = v20;
    v12 = v9;
    v13 = 1;
    if ( !Pointer )
    {
      v7 = 0;
      v4 = HandleTable::Emplace<ChannelEnumObject,wchar_t * * &,unsigned long &>(v20, &v7, &v21, &v20);
      if ( v4 )
      {
        *(_QWORD *)(v4 + 16) = v7;
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 24));
        v22 = v4;
        v7 = 0;
        EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v7);
        Pointer = 0;
      }
      else
      {
        Pointer = 14;
      }
    }
    tlx::_UndoSolo__ChannelConfigObject::GetProperty_::_8_::_lambda_1___::__UndoSolo__ChannelConfigObject::GetProperty_::_8_::_lambda_1___(&v10);
    wmi::AutoRef<Object>::Release(&v8);
  }
  catch ( EvtException *v19 )
  {
    v20 = *((_DWORD *)v19 + 6);
    Pointer = v20;
  }
  if ( Flags )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    pExceptionObject = 0;
    v15 = 0;
    v16 = 87;
    v17 = -1;
    v18 = 1345;
    throw (EvtException *)&pExceptionObject;
  }
  GetSession(&v8);
  v21 = 0;
  v20 = 0;
}

```

## disassembly

```asm
0x1800261d0  mov     rax, rsp
0x1800261d3  mov     [rax+8], rbx
0x1800261d7  push    rdi
0x1800261d8  sub     rsp, 0A0h
0x1800261df  mov     ebx, edx
0x1800261e1  mov     rdi, rcx
0x1800261e4  mov     qword ptr [rax+20h], 0
0x1800261ec  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x1800261f1  test    ebx, ebx
0x1800261f3  jz      short loc_180026274
0x1800261f5  lea     rax, WPP_GLOBAL_Control
0x1800261fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180026203  cmp     rcx, rax
0x180026206  jz      short loc_18002622D
0x180026208  test    byte ptr [rcx+1Ch], 1
0x18002620c  jz      short loc_18002622D
0x18002620e  cmp     byte ptr [rcx+19h], 2
0x180026212  jb      short loc_18002622D
0x180026214  mov     edx, 2Bh ; '+'
0x180026219  lea     r9d, [rdx+2Ch]
0x18002621d  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180026224  mov     rcx, [rcx+10h]
0x180026228  call    WPP_SF_D
0x18002622d  xorps   xmm0, xmm0
0x180026230  movdqu  [rsp+0A8h+pExceptionObject], xmm0
0x180026236  mov     [rsp+0A8h+var_28], 0
0x180026242  mov     [rsp+0A8h+var_20], 57h ; 'W'
0x18002624d  mov     [rsp+0A8h+var_1C], 0FFFFFFFFh
0x180026258  mov     [rsp+0A8h+var_18], 541h
0x180026263  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002626a  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18002626f  call    _CxxThrowException_0
0x180026274  mov     rdx, rdi
0x180026277  lea     rcx, [rsp+0A8h+var_60]; void *
0x18002627c  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x180026281  nop
0x180026282  mov     [rsp+0A8h+arg_10], 0
0x18002628e  mov     [rsp+0A8h+arg_8], 0
0x180026299  lea     rax, [rsp+0A8h+arg_10]
0x1800262a1  mov     [rsp+0A8h+var_78], rax
0x1800262a6  lea     rax, [rsp+0A8h+arg_8]
0x1800262ae  mov     [rsp+0A8h+var_80], rax
0x1800262b3  mov     [rsp+0A8h+var_88], 0
0x1800262bb  mov     r9, [rsp+0A8h+var_60]
0x1800262c0  mov     r9, [r9+48h]
0x1800262c4  xor     r8d, r8d; pReturnValue
0x1800262c7  lea     edx, [r8+13h]; nProcNum
0x1800262cb  lea     rcx, pProxyInfo; pProxyInfo
0x1800262d2  call    cs:__imp_NdrClientCall3
0x1800262d8  mov     rbx, rax
0x1800262db  mov     rax, [rsp+0A8h+arg_10]
0x1800262e3  mov     ecx, [rsp+0A8h+arg_8]
0x1800262ea  mov     [rsp+0A8h+var_50], rax
0x1800262ef  mov     [rsp+0A8h+var_48], ecx
0x1800262f3  mov     eax, [rsp+0A8h+var_54]
0x1800262f7  mov     [rsp+0A8h+var_44], eax
0x1800262fb  mov     [rsp+0A8h+var_40], 1
0x180026300  test    ebx, ebx
0x180026302  jnz     short loc_180026362
0x180026304  mov     [rsp+0A8h+var_68], 0
0x18002630d  lea     r9, [rsp+0A8h+arg_8]
0x180026315  lea     r8, [rsp+0A8h+arg_10]
0x18002631d  lea     rdx, [rsp+0A8h+var_68]
0x180026322  call    ??$Emplace@VChannelEnumObject@@AEAPEAPEA_WAEAK@HandleTable@@QEAAPEAVChannelEnumObject@@AEAPEAXAEAPEAPEA_WAEAK@Z; HandleTable::Emplace<ChannelEnumObject,wchar_t * * &,ulong &>(void * &,wchar_t * * &,ulong &)
0x180026327  mov     rcx, rax
0x18002632a  test    rax, rax
0x18002632d  jnz     short loc_180026334
0x18002632f  lea     ebx, [rax+0Eh]
0x180026332  jmp     short loc_180026362
0x180026334  mov     rax, [rsp+0A8h+var_68]
0x180026339  mov     [rcx+10h], rax
0x18002633d  lock inc dword ptr [rcx+8]
0x180026341  lock inc dword ptr [rcx+18h]
0x180026345  mov     [rsp+0A8h+arg_18], rcx
0x18002634d  mov     [rsp+0A8h+var_68], 0
0x180026356  lea     rcx, [rsp+0A8h+var_68]; this
0x18002635b  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x180026360  xor     ebx, ebx
0x180026362  lea     rcx, [rsp+0A8h+var_50]
0x180026367  call    tlx___UndoSolo__ChannelConfigObject__GetProperty____8____lambda_1_______UndoSolo__ChannelConfigObject__GetProperty____8____lambda_1___
0x18002636c  nop
0x18002636d  lea     rcx, [rsp+0A8h+var_60]; void *
0x180026372  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180026377  nop
0x180026378  jmp     short loc_180026381
0x18002637a  mov     ebx, [rsp+0A8h+arg_8]
0x180026381  mov     ecx, ebx; dwErrCode
0x180026383  call    cs:__imp_SetLastError
0x180026389  lea     rcx, [rsp+0A8h+arg_18]; this
0x180026391  call    ?Detach@EvtHandleRef@@QEAAPEAXXZ; EvtHandleRef::Detach(void)
0x180026396  mov     rbx, rax
0x180026399  lea     rcx, [rsp+0A8h+arg_18]; this
0x1800263a1  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x1800263a6  mov     rax, rbx
0x1800263a9  mov     rbx, [rsp+0A8h+arg_0]
0x1800263b1  add     rsp, 0A0h
0x1800263b8  pop     rdi
0x1800263b9  retn
```
