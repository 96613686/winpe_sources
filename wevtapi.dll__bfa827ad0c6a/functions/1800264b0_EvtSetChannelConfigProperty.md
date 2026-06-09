# EvtSetChannelConfigProperty

- ea: `0x1800264b0`
- end: `0x1800265ca`
- name: `EvtSetChannelConfigProperty`
- size: `282`
- prototype: `BOOL __stdcall(EVT_HANDLE ChannelConfig, EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId, DWORD Flags, PEVT_VARIANT PropertyValue)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180010840`
- `0x180023548`
- `0x1800264b0`
- `0x180027a88`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800265a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800265a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall EvtSetChannelConfigProperty(
        EVT_HANDLE ChannelConfig,
        EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId,
        DWORD Flags,
        PEVT_VARIANT PropertyValue)
{
  __int64 v8; // rcx
  BOOL v9; // edi
  DWORD ReferencedObjectAs; // esi
  struct _EVT_VARIANT *v11; // r8
  ChannelConfigObject *v12; // rbx
  ChannelConfigObject *v14; // [rsp+20h] [rbp-58h] BYREF
  EvtException *v15; // [rsp+28h] [rbp-50h] BYREF
  __int128 pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+40h] [rbp-38h]
  int v18; // [rsp+48h] [rbp-30h]
  int v19; // [rsp+4Ch] [rbp-2Ch]
  int v20; // [rsp+50h] [rbp-28h]

  LastErrInfo::Reset((LastErrInfo *)ChannelConfig);
  try
  {
    v9 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v17 = 0;
      v18 = 87;
      v19 = -1;
      v20 = 1517;
      throw (EvtException *)&pExceptionObject;
    }
    if ( PropertyValue )
    {
      v14 = 0;
      ReferencedObjectAs = ObjectTable::GetReferencedObjectAsType<ChannelConfigObject,void>(v8, ChannelConfig, &v14);
      if ( ReferencedObjectAs )
      {
        v12 = v14;
      }
      else
      {
        v11 = PropertyValue;
        v12 = v14;
        ReferencedObjectAs = ChannelConfigObject::SetProperty(v14, PropertyId, v11);
      }
      if ( v12 )
        wmi::RefBase::Release(v12);
    }
    else
    {
      ReferencedObjectAs = 87;
    }
  }
  catch ( EvtException *v15 )
  {
    v9 = 0;
    ReferencedObjectAs = *((_DWORD *)v15 + 6);
  }
  SetLastError(ReferencedObjectAs);
  LOBYTE(v9) = ReferencedObjectAs == 0;
  return v9;
}

```

## disassembly

```asm
0x1800264b0  mov     [rsp+arg_0], rbx
0x1800264b5  mov     [rsp+arg_8], rsi
0x1800264ba  push    rdi
0x1800264bb  push    r14
0x1800264bd  push    r15
0x1800264bf  sub     rsp, 60h
0x1800264c3  mov     rbx, r9
0x1800264c6  mov     esi, r8d
0x1800264c9  mov     r15d, edx
0x1800264cc  mov     r14, rcx
0x1800264cf  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x1800264d4  xor     edi, edi
0x1800264d6  test    esi, esi
0x1800264d8  jz      short loc_18002654C
0x1800264da  lea     rax, WPP_GLOBAL_Control
0x1800264e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264e8  cmp     rcx, rax
0x1800264eb  jz      short loc_180026514
0x1800264ed  test    byte ptr [rcx+1Ch], 1
0x1800264f1  jz      short loc_180026514
0x1800264f3  cmp     byte ptr [rcx+19h], 2
0x1800264f7  jb      short loc_180026514
0x1800264f9  lea     edx, [rdi+2Fh]
0x1800264fc  lea     esi, [rdi+57h]
0x1800264ff  mov     r9d, esi
0x180026502  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180026509  mov     rcx, [rcx+10h]
0x18002650d  call    WPP_SF_D
0x180026512  jmp     short loc_180026519
0x180026514  mov     esi, 57h ; 'W'
0x180026519  xorps   xmm0, xmm0
0x18002651c  movdqu  [rsp+78h+pExceptionObject], xmm0
0x180026522  mov     [rsp+78h+var_38], rdi
0x180026527  mov     [rsp+78h+var_30], esi
0x18002652b  mov     [rsp+78h+var_2C], 0FFFFFFFFh
0x180026533  mov     [rsp+78h+var_28], 5EDh
0x18002653b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026542  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180026547  call    _CxxThrowException_0
0x18002654c  test    rbx, rbx
0x18002654f  jz      short loc_180026594
0x180026551  mov     [rsp+78h+var_58], rdi
0x180026556  lea     r8, [rsp+78h+var_58]
0x18002655b  mov     rdx, r14
0x18002655e  call    ??$GetReferencedObjectAsType@VChannelConfigObject@@X@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VChannelConfigObject@@@wmi@@@Z; ObjectTable::GetReferencedObjectAsType<ChannelConfigObject,void>(void *,wmi::AutoRef<ChannelConfigObject> &)
0x180026563  mov     esi, eax
0x180026565  test    eax, eax
0x180026567  jnz     short loc_180026580
0x180026569  mov     r8, rbx; struct _EVT_VARIANT *
0x18002656c  mov     edx, r15d; unsigned int
0x18002656f  mov     rbx, [rsp+78h+var_58]
0x180026574  mov     rcx, rbx; this
0x180026577  call    ?SetProperty@ChannelConfigObject@@QEAAKKPEAU_EVT_VARIANT@@@Z; ChannelConfigObject::SetProperty(ulong,_EVT_VARIANT *)
0x18002657c  mov     esi, eax
0x18002657e  jmp     short loc_180026585
0x180026580  mov     rbx, [rsp+78h+var_58]
0x180026585  test    rbx, rbx
0x180026588  jz      short loc_180026599
0x18002658a  mov     rcx, rbx; this
0x18002658d  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x180026592  jmp     short loc_180026599
0x180026594  mov     esi, 57h ; 'W'
0x180026599  jmp     short loc_1800265A4
0x18002659b  xor     edi, edi
0x18002659d  mov     esi, [rsp+78h+arg_10]
0x1800265a4  mov     ecx, esi; dwErrCode
0x1800265a6  call    cs:__imp_SetLastError
0x1800265ac  test    esi, esi
0x1800265ae  setz    dil
0x1800265b2  mov     eax, edi
0x1800265b4  lea     r11, [rsp+78h+var_18]
0x1800265b9  mov     rbx, [r11+20h]
0x1800265bd  mov     rsi, [r11+28h]
0x1800265c1  mov     rsp, r11
0x1800265c4  pop     r15
0x1800265c6  pop     r14
0x1800265c8  pop     rdi
0x1800265c9  retn
```
