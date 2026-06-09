# GetPublisherCommand::GetPropertyArray(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong &)

- ea: `0x14000e31c`
- end: `0x14000e542`
- name: `?GetPropertyArray@GetPublisherCommand@@AEAAPEAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@AEAK@Z`
- size: `550`
- prototype: `void *__fastcall(GetPublisherCommand *this, const wchar_t *, void *, EVT_PUBLISHER_METADATA_PROPERTY_ID, unsigned int *ObjectArraySize)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000db10`

## callees

- `0x14000a574`
- `0x14000e31c`
- `0x140010450`
- `0x140022cec`
- `0x14002924c`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e48f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e48f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x14000e49a`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x14000e49a`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtGetObjectArraySize` at `0x14000e481`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtGetObjectArraySize` at `0x14000e481`

## pseudocode

```c
void *__fastcall GetPublisherCommand::GetPropertyArray(
        GetPublisherCommand *this,
        const wchar_t *a2,
        void *a3,
        EVT_PUBLISHER_METADATA_PROPERTY_ID a4,
        unsigned int *ObjectArraySize)
{
  unsigned int PublisherProperty; // eax
  unsigned int v7; // ebx
  DWORD LastError; // edi
  const char *v10; // [rsp+20h] [rbp-31h]
  _BYTE pExceptionObject[72]; // [rsp+58h] [rbp+7h] BYREF

  PublisherProperty = GetPublisherProperty(a3, a4);
  v7 = PublisherProperty;
  if ( PublisherProperty )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids,
        PublisherProperty);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v7, 0, 0, v10, 187, 4u, a2);
    throw (EvtException *)pExceptionObject;
  }
  if ( !MEMORY[0xC] )
    return 0;
  if ( MEMORY[0xC] != 32 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, 0, 0, v10, 197, 4u, a2);
    throw (EvtException *)pExceptionObject;
  }
  if ( !EvtGetObjectArraySize(MEMORY[0], ObjectArraySize) )
  {
    LastError = GetLastError();
    EvtClose(MEMORY[0]);
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v10, 204, 4u, a2);
    throw (EvtException *)pExceptionObject;
  }
  return (void *)MEMORY[0];
}

```

## disassembly

```asm
0x14000e31c  mov     [rsp-8+arg_0], rcx
0x14000e321  push    rbp
0x14000e322  push    rbx
0x14000e323  push    rsi
0x14000e324  push    rdi
0x14000e325  lea     rbp, [rsp-37h]
0x14000e32a  sub     rsp, 88h
0x14000e331  mov     eax, r9d
0x14000e334  mov     rcx, r8; PublisherMetadata
0x14000e337  mov     rsi, rdx
0x14000e33a  xorps   xmm0, xmm0
0x14000e33d  movdqu  [rbp+4Fh+var_60], xmm0
0x14000e342  mov     [rbp+4Fh+var_50], 0
0x14000e34a  mov     [rbp+4Fh+arg_0], 0
0x14000e352  lea     r9, [rbp+4Fh+arg_0]
0x14000e356  lea     r8, [rbp+4Fh+var_60]
0x14000e35a  mov     edx, eax; PropertyId
0x14000e35c  call    ?GetPublisherProperty@@YAKPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z; GetPublisherProperty(void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,std::vector<uchar> &,_EVT_VARIANT * &)
0x14000e361  mov     ebx, eax
0x14000e363  test    eax, eax
0x14000e365  jz      short loc_14000E3DA
0x14000e367  lea     rcx, WPP_GLOBAL_Control
0x14000e36e  mov     r10, cs:WPP_GLOBAL_Control
0x14000e375  cmp     r10, rcx
0x14000e378  jz      short loc_14000E3A3
0x14000e37a  test    dword ptr [r10+1Ch], 400000h
0x14000e382  jz      short loc_14000E3A3
0x14000e384  cmp     byte ptr [r10+19h], 2
0x14000e389  jb      short loc_14000E3A3
0x14000e38b  mov     edx, 0Fh
0x14000e390  mov     r9d, eax
0x14000e393  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x14000e39a  mov     rcx, [r10+10h]
0x14000e39e  call    WPP_SF_d
0x14000e3a3  mov     [rsp+0A0h+Src], rsi; Src
0x14000e3a8  mov     [rsp+0A0h+var_70], 4; unsigned int
0x14000e3b0  mov     [rsp+0A0h+var_78], 0BBh; int
0x14000e3b8  xor     r9d, r9d; unsigned int
0x14000e3bb  xor     r8d, r8d; unsigned int
0x14000e3be  mov     edx, ebx; unsigned int
0x14000e3c0  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x14000e3c4  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000e3c9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000e3d0  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14000e3d4  call    _CxxThrowException_0
0x14000e3da  mov     rbx, [rbp+4Fh+arg_0]
0x14000e3de  cmp     dword ptr [rbx+0Ch], 0
0x14000e3e2  jnz     short loc_14000E400
0x14000e3e4  mov     rcx, qword ptr [rbp+4Fh+var_60]
0x14000e3e8  test    rcx, rcx
0x14000e3eb  jz      short loc_14000E3F9
0x14000e3ed  mov     rdx, [rbp+4Fh+var_50]
0x14000e3f1  sub     rdx, rcx
0x14000e3f4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000e3f9  xor     eax, eax
0x14000e3fb  jmp     loc_14000E536
0x14000e400  cmp     dword ptr [rbx+0Ch], 20h ; ' '
0x14000e404  jz      short loc_14000E47A
0x14000e406  lea     rcx, WPP_GLOBAL_Control
0x14000e40d  mov     ebx, 0Dh
0x14000e412  mov     rax, cs:WPP_GLOBAL_Control
0x14000e419  cmp     rax, rcx
0x14000e41c  jz      short loc_14000E443
0x14000e41e  test    dword ptr [rax+1Ch], 400000h
0x14000e425  jz      short loc_14000E443
0x14000e427  cmp     byte ptr [rax+19h], 2
0x14000e42b  jb      short loc_14000E443
0x14000e42d  lea     edx, [rbx+3]
0x14000e430  mov     r9d, ebx
0x14000e433  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x14000e43a  mov     rcx, [rax+10h]
0x14000e43e  call    WPP_SF_d
0x14000e443  mov     [rsp+0A0h+Src], rsi; Src
0x14000e448  mov     [rsp+0A0h+var_70], 4; unsigned int
0x14000e450  mov     [rsp+0A0h+var_78], 0C5h; int
0x14000e458  xor     r9d, r9d; unsigned int
0x14000e45b  xor     r8d, r8d; unsigned int
0x14000e45e  mov     edx, ebx; unsigned int
0x14000e460  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x14000e464  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000e469  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000e470  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14000e474  call    _CxxThrowException_0
0x14000e47a  mov     rdx, [rbp+4Fh+ObjectArraySize]; ObjectArraySize
0x14000e47e  mov     rcx, [rbx]; ObjectArray
0x14000e481  call    cs:__imp_EvtGetObjectArraySize
0x14000e487  test    eax, eax
0x14000e489  jnz     loc_14000E51B
0x14000e48f  call    cs:__imp_GetLastError
0x14000e495  mov     edi, eax
0x14000e497  mov     rcx, [rbx]; Object
0x14000e49a  call    cs:__imp_EvtClose
0x14000e4a0  mov     eax, 507h
0x14000e4a5  test    edi, edi
0x14000e4a7  cmovz   edi, eax
0x14000e4aa  lea     rcx, WPP_GLOBAL_Control
0x14000e4b1  mov     rax, cs:WPP_GLOBAL_Control
0x14000e4b8  cmp     rax, rcx
0x14000e4bb  jz      short loc_14000E4E4
0x14000e4bd  test    dword ptr [rax+1Ch], 400000h
0x14000e4c4  jz      short loc_14000E4E4
0x14000e4c6  cmp     byte ptr [rax+19h], 2
0x14000e4ca  jb      short loc_14000E4E4
0x14000e4cc  mov     edx, 11h
0x14000e4d1  mov     r9d, edi
0x14000e4d4  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x14000e4db  mov     rcx, [rax+10h]
0x14000e4df  call    WPP_SF_d
0x14000e4e4  mov     [rsp+0A0h+Src], rsi; Src
0x14000e4e9  mov     [rsp+0A0h+var_70], 4; unsigned int
0x14000e4f1  mov     [rsp+0A0h+var_78], 0CCh; int
0x14000e4f9  xor     r9d, r9d; unsigned int
0x14000e4fc  xor     r8d, r8d; unsigned int
0x14000e4ff  mov     edx, edi; unsigned int
0x14000e501  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x14000e505  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000e50a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000e511  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14000e515  call    _CxxThrowException_0
0x14000e51b  mov     rbx, [rbx]
0x14000e51e  mov     rcx, qword ptr [rbp+4Fh+var_60]
0x14000e522  test    rcx, rcx
0x14000e525  jz      short loc_14000E533
0x14000e527  mov     rdx, [rbp+4Fh+var_50]
0x14000e52b  sub     rdx, rcx
0x14000e52e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000e533  mov     rax, rbx
0x14000e536  add     rsp, 88h
0x14000e53d  pop     rdi
0x14000e53e  pop     rsi
0x14000e53f  pop     rbx
0x14000e540  pop     rbp
0x14000e541  retn
```
