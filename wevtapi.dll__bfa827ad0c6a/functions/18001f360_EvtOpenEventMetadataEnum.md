# EvtOpenEventMetadataEnum

- ea: `0x18001f360`
- end: `0x18001f4b9`
- name: `EvtOpenEventMetadataEnum`
- size: `345`
- prototype: `EVT_HANDLE __stdcall(EVT_HANDLE PublisherMetadata, DWORD Flags)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180007010`
- `0x180008924`
- `0x18001043c`
- `0x18001f360`
- `0x180023548`
- `0x18002366c`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f471`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f471`

## pseudocode

```c
EVT_HANDLE __stdcall EvtOpenEventMetadataEnum(EVT_HANDLE PublisherMetadata, DWORD Flags)
{
  __int64 v4; // rcx
  DWORD ReferencedObjectAs; // r14d
  wmi::RefBase *v6; // rbx
  wmi::RefBase *v7; // rdi
  ObjectTable *v8; // rcx
  __int64 v9; // rax
  void *v10; // rbx
  wmi::RefBase *v12; // [rsp+20h] [rbp-58h] BYREF
  EvtException *v13; // [rsp+28h] [rbp-50h] BYREF
  __int128 pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h]
  int v16; // [rsp+48h] [rbp-30h]
  int v17; // [rsp+4Ch] [rbp-2Ch]
  int v18; // [rsp+50h] [rbp-28h]
  __int64 v19; // [rsp+90h] [rbp+18h] BYREF
  wmi::RefBase *v20; // [rsp+98h] [rbp+20h] BYREF

  v19 = 0;
  LastErrInfo::Reset((LastErrInfo *)PublisherMetadata);
  try
  {
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v15 = 0;
      v16 = 87;
      v17 = -1;
      v18 = 1850;
      throw (EvtException *)&pExceptionObject;
    }
    v20 = 0;
    ReferencedObjectAs = ObjectTable::GetReferencedObjectAsType<PublisherMetadataObject,void>(
                           v4,
                           PublisherMetadata,
                           &v20);
    v6 = v20;
    if ( !ReferencedObjectAs )
    {
      PublisherMetadataObject::GetEventMetadataEnum(v20, &v12);
      v7 = v12;
      ReferencedObjectAs = ObjectTable::AddObject(v8, v12, (struct EvtHandleRef *)&v19);
      if ( v7 )
        wmi::RefBase::Release(v7);
    }
    if ( v6 )
      wmi::RefBase::Release(v6);
  }
  catch ( EvtException *v13 )
  {
    ReferencedObjectAs = *((_DWORD *)v13 + 6);
  }
  if ( Flags )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    pExceptionObject = 0;
    v15 = 0;
    v16 = 87;
    v17 = -1;
    v18 = 1850;
    throw (EvtException *)&pExceptionObject;
  }
  v20 = 0;
  ReferencedObjectAs = ObjectTable::GetReferencedObjectAsType<PublisherMetadataObject,void>(v4, PublisherMetadata, &v20);
  v6 = v20;
  if ( !ReferencedObjectAs )
  {
    PublisherMetadataObject::GetEventMetadataEnum(v20, &v12);
    v7 = v12;
    ReferencedObjectAs = ObjectTable::AddObject(v8, v12, (struct EvtHandleRef *)&v19);
    if ( v7 )
      wmi::RefBase::Release(v7);
  }
}

```

## disassembly

```asm
0x18001f360  mov     rax, rsp
0x18001f363  push    rbx
0x18001f364  push    rdi
0x18001f365  push    r14
0x18001f367  sub     rsp, 60h
0x18001f36b  mov     ebx, edx
0x18001f36d  mov     rdi, rcx
0x18001f370  mov     qword ptr [rax+18h], 0
0x18001f378  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18001f37d  test    ebx, ebx
0x18001f37f  jz      short loc_18001F3F8
0x18001f381  lea     rax, WPP_GLOBAL_Control
0x18001f388  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f38f  cmp     rcx, rax
0x18001f392  jz      short loc_18001F3BD
0x18001f394  mov     edx, 1
0x18001f399  test    [rcx+1Ch], dl
0x18001f39c  jz      short loc_18001F3BD
0x18001f39e  cmp     byte ptr [rcx+19h], 2
0x18001f3a2  jb      short loc_18001F3BD
0x18001f3a4  mov     edx, 35h ; '5'
0x18001f3a9  lea     r9d, [rdx+22h]
0x18001f3ad  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001f3b4  mov     rcx, [rcx+10h]
0x18001f3b8  call    WPP_SF_D
0x18001f3bd  xorps   xmm0, xmm0
0x18001f3c0  movdqu  [rsp+78h+pExceptionObject], xmm0
0x18001f3c6  mov     [rsp+78h+var_38], 0
0x18001f3cf  mov     [rsp+78h+var_30], 57h ; 'W'
0x18001f3d7  mov     [rsp+78h+var_2C], 0FFFFFFFFh
0x18001f3df  mov     [rsp+78h+var_28], 73Ah
0x18001f3e7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001f3ee  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001f3f3  call    _CxxThrowException_0
0x18001f3f8  mov     [rsp+78h+arg_18], 0
0x18001f404  lea     r8, [rsp+78h+arg_18]
0x18001f40c  mov     rdx, rdi
0x18001f40f  call    ??$GetReferencedObjectAsType@VPublisherMetadataObject@@X@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VPublisherMetadataObject@@@wmi@@@Z; ObjectTable::GetReferencedObjectAsType<PublisherMetadataObject,void>(void *,wmi::AutoRef<PublisherMetadataObject> &)
0x18001f414  mov     r14d, eax
0x18001f417  mov     rbx, [rsp+78h+arg_18]
0x18001f41f  test    eax, eax
0x18001f421  jnz     short loc_18001F456
0x18001f423  lea     rdx, [rsp+78h+var_58]
0x18001f428  mov     rcx, rbx
0x18001f42b  call    ?GetEventMetadataEnum@PublisherMetadataObject@@QEAA?AV?$AutoRef@VEventMetadataEnumObject@@@wmi@@XZ; PublisherMetadataObject::GetEventMetadataEnum(void)
0x18001f430  lea     r8, [rsp+78h+arg_10]; struct EvtHandleRef *
0x18001f438  mov     rdi, [rsp+78h+var_58]
0x18001f43d  mov     rdx, rdi; struct Object *
0x18001f440  call    ?AddObject@ObjectTable@@QEAAKPEAVObject@@AEAVEvtHandleRef@@@Z; ObjectTable::AddObject(Object *,EvtHandleRef &)
0x18001f445  mov     r14d, eax
0x18001f448  test    rdi, rdi
0x18001f44b  jz      short loc_18001F456
0x18001f44d  mov     rcx, rdi; this
0x18001f450  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18001f455  nop
0x18001f456  test    rbx, rbx
0x18001f459  jz      short loc_18001F464
0x18001f45b  mov     rcx, rbx; this
0x18001f45e  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18001f463  nop
0x18001f464  jmp     short loc_18001F46E
0x18001f466  mov     r14d, [rsp+78h+arg_8]
0x18001f46e  mov     ecx, r14d; dwErrCode
0x18001f471  call    cs:__imp_SetLastError
0x18001f477  mov     rax, [rsp+78h+arg_10]
0x18001f47f  test    rax, rax
0x18001f482  jz      short loc_18001F49E
0x18001f484  mov     rbx, [rax+10h]
0x18001f488  mov     [rsp+78h+arg_10], 0
0x18001f494  mov     edx, 1
0x18001f499  xchg    dl, [rax+1Dh]
0x18001f49c  jmp     short loc_18001F4A0
0x18001f49e  xor     ebx, ebx
0x18001f4a0  lea     rcx, [rsp+78h+arg_10]; this
0x18001f4a8  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001f4ad  mov     rax, rbx
0x18001f4b0  add     rsp, 60h
0x18001f4b4  pop     r14
0x18001f4b6  pop     rdi
0x18001f4b7  pop     rbx
0x18001f4b8  retn
```
