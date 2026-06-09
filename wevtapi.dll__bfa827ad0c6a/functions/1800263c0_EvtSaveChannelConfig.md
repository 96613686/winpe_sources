# EvtSaveChannelConfig

- ea: `0x1800263c0`
- end: `0x1800264a8`
- name: `EvtSaveChannelConfig`
- size: `232`
- prototype: `BOOL __stdcall(EVT_HANDLE ChannelConfig, DWORD Flags)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180010840`
- `0x180023548`
- `0x1800263c0`
- `0x1800278cc`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002648a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002648a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall EvtSaveChannelConfig(EVT_HANDLE ChannelConfig, DWORD Flags)
{
  __int64 v4; // rcx
  BOOL v5; // edi
  DWORD ReferencedObjectAs; // esi
  ChannelConfigObject *v7; // rbx
  EvtException *v9; // [rsp+20h] [rbp-38h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h]
  int v12; // [rsp+40h] [rbp-18h]
  int v13; // [rsp+44h] [rbp-14h]
  int v14; // [rsp+48h] [rbp-10h]
  ChannelConfigObject *v15; // [rsp+70h] [rbp+18h] BYREF

  LastErrInfo::Reset((LastErrInfo *)ChannelConfig);
  try
  {
    v5 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v11 = 0;
      v12 = 87;
      v13 = -1;
      v14 = 1478;
      throw (EvtException *)&pExceptionObject;
    }
    v15 = 0;
    ReferencedObjectAs = ObjectTable::GetReferencedObjectAsType<ChannelConfigObject,void>(v4, ChannelConfig, &v15);
    v7 = v15;
    if ( !ReferencedObjectAs )
      ChannelConfigObject::Save(v15);
    if ( v7 )
      wmi::RefBase::Release(v7);
  }
  catch ( EvtException *v9 )
  {
    v5 = 0;
    ReferencedObjectAs = *((_DWORD *)v9 + 6);
  }
  SetLastError(ReferencedObjectAs);
  LOBYTE(v5) = ReferencedObjectAs == 0;
  return v5;
}

```

## disassembly

```asm
0x1800263c0  mov     [rsp+arg_0], rbx
0x1800263c5  mov     [rsp+arg_18], rsi
0x1800263ca  push    rdi
0x1800263cb  sub     rsp, 50h
0x1800263cf  mov     ebx, edx
0x1800263d1  mov     rsi, rcx
0x1800263d4  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x1800263d9  xor     edi, edi
0x1800263db  test    ebx, ebx
0x1800263dd  jz      short loc_18002644C
0x1800263df  lea     rax, WPP_GLOBAL_Control
0x1800263e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263ed  cmp     rcx, rax
0x1800263f0  jz      short loc_180026415
0x1800263f2  test    byte ptr [rcx+1Ch], 1
0x1800263f6  jz      short loc_180026415
0x1800263f8  cmp     byte ptr [rcx+19h], 2
0x1800263fc  jb      short loc_180026415
0x1800263fe  lea     edx, [rdi+2Eh]
0x180026401  lea     r9d, [rdi+57h]
0x180026405  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18002640c  mov     rcx, [rcx+10h]
0x180026410  call    WPP_SF_D
0x180026415  xorps   xmm0, xmm0
0x180026418  movdqu  [rsp+58h+pExceptionObject], xmm0
0x18002641e  mov     [rsp+58h+var_20], rdi
0x180026423  mov     [rsp+58h+var_18], 57h ; 'W'
0x18002642b  mov     [rsp+58h+var_14], 0FFFFFFFFh
0x180026433  mov     [rsp+58h+var_10], 5C6h
0x18002643b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026442  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180026447  call    _CxxThrowException_0
0x18002644c  mov     [rsp+58h+arg_10], rdi
0x180026451  lea     r8, [rsp+58h+arg_10]
0x180026456  mov     rdx, rsi
0x180026459  call    ??$GetReferencedObjectAsType@VChannelConfigObject@@X@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VChannelConfigObject@@@wmi@@@Z; ObjectTable::GetReferencedObjectAsType<ChannelConfigObject,void>(void *,wmi::AutoRef<ChannelConfigObject> &)
0x18002645e  mov     esi, eax
0x180026460  mov     rbx, [rsp+58h+arg_10]
0x180026465  test    eax, eax
0x180026467  jnz     short loc_180026472
0x180026469  mov     rcx, rbx; this
0x18002646c  call    ?Save@ChannelConfigObject@@QEAAXXZ; ChannelConfigObject::Save(void)
0x180026471  nop
0x180026472  test    rbx, rbx
0x180026475  jz      short loc_180026480
0x180026477  mov     rcx, rbx; this
0x18002647a  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18002647f  nop
0x180026480  jmp     short loc_180026488
0x180026482  xor     edi, edi
0x180026484  mov     esi, [rsp+58h+arg_8]
0x180026488  mov     ecx, esi; dwErrCode
0x18002648a  call    cs:__imp_SetLastError
0x180026490  test    esi, esi
0x180026492  setz    dil
0x180026496  mov     eax, edi
0x180026498  mov     rbx, [rsp+58h+arg_0]
0x18002649d  mov     rsi, [rsp+58h+arg_18]
0x1800264a2  add     rsp, 50h
0x1800264a6  pop     rdi
0x1800264a7  retn
```
