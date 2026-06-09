# WcExpandDirectory

- ea: `0x140017f64`
- end: `0x14001824e`
- name: `WcExpandDirectory`
- size: `746`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1400184f0`

## callees

- `0x140002294`
- `0x1400024fc`
- `0x1400048a4`
- `0x140017f64`
- `0x140018b9c`
- `0x1400196e0`
- `0x14001e374`
- `0x14001fc48`
- `0x140020988`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140018023`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018023`
- `ntoskrnl!ObfDereferenceObject` at `0x14001822f`
- `ntoskrnl!ObfDereferenceObject` at `0x14001822f`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400180b5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140018184`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400180b5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140018184`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400181a0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400181a0`
- `FLTMGR!FltClose` at `0x14001821a`
- `FLTMGR!FltClose` at `0x14001821a`

## pseudocode

```c
__int64 __fastcall WcExpandDirectory(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64 a3, _QWORD *a4)
{
  __int64 v4; // rax
  __int64 v7; // rdx
  __int64 *v10; // rdx
  int v11; // edx
  int v12; // edi
  _QWORD *Source; // rax
  int v14; // eax
  int v15; // edx
  HANDLE FileHandle; // [rsp+50h] [rbp-19h] BYREF
  PVOID Object; // [rsp+58h] [rbp-11h] BYREF
  __int64 v19; // [rsp+60h] [rbp-9h] BYREF
  __int128 v20; // [rsp+68h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp+Fh] BYREF
  char v22; // [rsp+E0h] [rbp+77h] BYREF

  v4 = *(_QWORD *)(a3 + 32);
  v20 = 0;
  FileHandle = 0;
  DestinationString = 0;
  Object = 0;
  v7 = *(_QWORD *)(v4 + 64);
  v22 = 0;
  v19 = 0;
  WORD1(v20) = *(_WORD *)(v7 + 32);
  LOWORD(v20) = WORD1(v20);
  *((_QWORD *)&v20 + 1) = v7 + 34;
  v10 = WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_sDZ(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      10,
      16,
      (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
      131,
      (__int64)&v20);
  }
  RtlInitUnicodeString(&DestinationString, 0);
  v12 = WcRelativeStreamOpen(Instance, FileObject, &DestinationString, &FileHandle, (PFILE_OBJECT *)&Object);
  if ( v12 >= 0 )
  {
    v12 = WcPopulateDirectory(
            a3 + 56,
            *(_QWORD *)(*(_QWORD *)(a3 + 32) + 64LL),
            FileHandle,
            Object,
            Instance,
            &v22,
            &v19);
    if ( v12 >= 0 )
    {
      if ( v22 )
      {
        v12 = WcUntagFile(Instance, FileObject);
        if ( v12 < 0 )
          goto LABEL_14;
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 32) + 8LL));
        *(_DWORD *)(*(_QWORD *)(a3 + 32) + 88LL) |= 1u;
        *(_DWORD *)(*(_QWORD *)(a3 + 32) + 88LL) &= ~2u;
      }
      else
      {
        Source = (_QWORD *)WcGetSource(a3);
        v14 = WcCopyFileMetaData(Source[1], Source[2], *Source, FileHandle, FileObject, Instance, 4);
        if ( v14 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 4;
          WPP_RECORDER_SF_sDZd(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            10,
            17,
            (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
            202,
            (__int64)&v20,
            v14);
        }
        v12 = WcSetPlaceHolderFlags(Instance, FileObject, *(_QWORD *)(a3 + 32), 4);
        if ( v12 < 0 )
          goto LABEL_14;
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 32) + 8LL));
        *(_DWORD *)(*(_QWORD *)(a3 + 32) + 88LL) |= 1u;
      }
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 32) + 8LL));
LABEL_14:
      if ( a4 )
        *a4 = v19;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_sDZd(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      10,
      18,
      (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
      228,
      (__int64)&v20,
      v12);
  }
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140017f64  push    rbp
0x140017f66  push    rbx
0x140017f67  push    rsi
0x140017f68  push    rdi
0x140017f69  push    r14
0x140017f6b  push    r15
0x140017f6d  lea     rbp, [rsp-2Fh]
0x140017f72  sub     rsp, 98h
0x140017f79  mov     rax, [r8+20h]
0x140017f7d  xorps   xmm0, xmm0
0x140017f80  movups  [rbp+57h+var_58], xmm0
0x140017f84  mov     [rbp+57h+FileHandle], 0
0x140017f8c  mov     r14, rdx
0x140017f8f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140017f93  mov     [rbp+57h+Object], 0
0x140017f9b  mov     r15, r9
0x140017f9e  mov     rdx, [rax+40h]
0x140017fa2  mov     rbx, r8
0x140017fa5  mov     rsi, rcx
0x140017fa8  mov     [rbp+57h+arg_10], 0
0x140017fac  mov     [rbp+57h+var_60], 0
0x140017fb4  movzx   eax, word ptr [rdx+20h]
0x140017fb8  mov     word ptr [rbp+57h+var_58+2], ax
0x140017fbc  mov     word ptr [rbp+57h+var_58], ax
0x140017fc0  lea     rax, [rdx+22h]
0x140017fc4  mov     qword ptr [rbp+57h+var_58+8], rax
0x140017fc8  lea     rax, WPP_RECORDER_INITIALIZED
0x140017fcf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017fd6  lea     rcx, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140017fdd  lea     rdx, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140017fe4  jz      short loc_14001801D
0x140017fe6  lea     rax, [rbp+57h+var_58]
0x140017fea  mov     r9d, 10h
0x140017ff0  mov     [rsp+0C0h+var_88], rax
0x140017ff5  mov     dword ptr [rsp+0C0h+var_90], 383h
0x140017ffd  mov     [rsp+0C0h+var_98], rcx
0x140018002  mov     rcx, cs:WPP_GLOBAL_Control
0x140018009  lea     r8d, [r9-6]
0x14001800d  mov     [rsp+0C0h+FileObject], rdx
0x140018012  mov     dl, 4
0x140018014  mov     rcx, [rcx+40h]
0x140018018  call    WPP_RECORDER_SF_sDZ
0x14001801d  xor     edx, edx; SourceString
0x14001801f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140018023  call    cs:__imp_RtlInitUnicodeString
0x14001802a  nop     dword ptr [rax+rax+00h]
0x14001802f  lea     rax, [rbp+57h+Object]
0x140018033  mov     rdx, r14
0x140018036  lea     r9, [rbp+57h+FileHandle]
0x14001803a  mov     [rsp+0C0h+FileObject], rax; FileObject
0x14001803f  lea     r8, [rbp+57h+DestinationString]
0x140018043  mov     rcx, rsi; Instance
0x140018046  call    WcRelativeStreamOpen
0x14001804b  mov     edi, eax
0x14001804d  test    eax, eax
0x14001804f  js      loc_1400181B8
0x140018055  mov     rdx, [rbx+20h]
0x140018059  lea     rax, [rbp+57h+var_60]
0x14001805d  mov     r9, [rbp+57h+Object]
0x140018061  lea     rcx, [rbx+38h]
0x140018065  mov     r8, [rbp+57h+FileHandle]
0x140018069  mov     [rsp+0C0h+var_90], rax
0x14001806e  lea     rax, [rbp+57h+arg_10]
0x140018072  mov     rdx, [rdx+40h]
0x140018076  mov     [rsp+0C0h+var_98], rax
0x14001807b  mov     [rsp+0C0h+FileObject], rsi
0x140018080  call    WcPopulateDirectory
0x140018085  mov     edi, eax
0x140018087  test    eax, eax
0x140018089  js      loc_1400181B8
0x14001808f  cmp     [rbp+57h+arg_10], 0
0x140018093  jz      short loc_1400180D6
0x140018095  mov     r8, rbx
0x140018098  mov     rdx, r14; FileObject
0x14001809b  mov     rcx, rsi; Instance
0x14001809e  call    WcUntagFile
0x1400180a3  mov     edi, eax
0x1400180a5  test    eax, eax
0x1400180a7  js      loc_1400181AC
0x1400180ad  mov     rcx, [rbx+20h]
0x1400180b1  add     rcx, 8; FastMutex
0x1400180b5  call    cs:__imp_ExAcquireFastMutex
0x1400180bc  nop     dword ptr [rax+rax+00h]
0x1400180c1  mov     rax, [rbx+20h]
0x1400180c5  or      dword ptr [rax+58h], 1
0x1400180c9  mov     rax, [rbx+20h]
0x1400180cd  and     dword ptr [rax+58h], 0FFFFFFFDh
0x1400180d1  jmp     loc_140018198
0x1400180d6  mov     rcx, rbx
0x1400180d9  call    WcGetSource
0x1400180de  mov     r9, [rbp+57h+FileHandle]
0x1400180e2  mov     dword ptr [rsp+0C0h+var_90], 4
0x1400180ea  mov     [rsp+0C0h+var_98], rsi
0x1400180ef  mov     r8, [rax]
0x1400180f2  mov     rdx, [rax+10h]
0x1400180f6  mov     rcx, [rax+8]
0x1400180fa  mov     [rsp+0C0h+FileObject], r14
0x1400180ff  call    WcCopyFileMetaData
0x140018104  test    eax, eax
0x140018106  jns     short loc_140018161
0x140018108  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001810f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140018116  jz      short loc_140018161
0x140018118  mov     rcx, cs:WPP_GLOBAL_Control
0x14001811f  mov     r9d, 11h
0x140018125  mov     [rsp+0C0h+var_80], eax
0x140018129  mov     dl, 4
0x14001812b  lea     rax, [rbp+57h+var_58]
0x14001812f  mov     [rsp+0C0h+var_88], rax
0x140018134  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x14001813b  mov     rcx, [rcx+40h]
0x14001813f  lea     r8d, [r9-7]
0x140018143  mov     dword ptr [rsp+0C0h+var_90], 3CAh
0x14001814b  mov     [rsp+0C0h+var_98], rax
0x140018150  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140018157  mov     [rsp+0C0h+FileObject], rax
0x14001815c  call    WPP_RECORDER_SF_sDZd
0x140018161  mov     r8, [rbx+20h]
0x140018165  mov     r9d, 4
0x14001816b  mov     rdx, r14
0x14001816e  mov     rcx, rsi
0x140018171  call    WcSetPlaceHolderFlags
0x140018176  mov     edi, eax
0x140018178  test    eax, eax
0x14001817a  js      short loc_1400181AC
0x14001817c  mov     rcx, [rbx+20h]
0x140018180  add     rcx, 8; FastMutex
0x140018184  call    cs:__imp_ExAcquireFastMutex
0x14001818b  nop     dword ptr [rax+rax+00h]
0x140018190  mov     rax, [rbx+20h]
0x140018194  or      dword ptr [rax+58h], 1
0x140018198  mov     rcx, [rbx+20h]
0x14001819c  add     rcx, 8; FastMutex
0x1400181a0  call    cs:__imp_ExReleaseFastMutex
0x1400181a7  nop     dword ptr [rax+rax+00h]
0x1400181ac  test    r15, r15
0x1400181af  jz      short loc_1400181B8
0x1400181b1  mov     rax, [rbp+57h+var_60]
0x1400181b5  mov     [r15], rax
0x1400181b8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400181bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400181c6  jz      short loc_140018211
0x1400181c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400181cf  lea     rax, [rbp+57h+var_58]
0x1400181d3  mov     [rsp+0C0h+var_80], edi
0x1400181d7  mov     r9d, 12h
0x1400181dd  mov     [rsp+0C0h+var_88], rax
0x1400181e2  mov     dl, 4
0x1400181e4  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x1400181eb  mov     dword ptr [rsp+0C0h+var_90], 3E4h
0x1400181f3  mov     rcx, [rcx+40h]
0x1400181f7  mov     [rsp+0C0h+var_98], rax
0x1400181fc  lea     r8d, [r9-8]
0x140018200  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140018207  mov     [rsp+0C0h+FileObject], rax
0x14001820c  call    WPP_RECORDER_SF_sDZd
0x140018211  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140018215  test    rcx, rcx
0x140018218  jz      short loc_140018226
0x14001821a  call    cs:__imp_FltClose
0x140018221  nop     dword ptr [rax+rax+00h]
0x140018226  mov     rcx, [rbp+57h+Object]; Object
0x14001822a  test    rcx, rcx
0x14001822d  jz      short loc_14001823B
0x14001822f  call    cs:__imp_ObfDereferenceObject
0x140018236  nop     dword ptr [rax+rax+00h]
0x14001823b  mov     eax, edi
0x14001823d  add     rsp, 98h
0x140018244  pop     r15
0x140018246  pop     r14
0x140018248  pop     rdi
0x140018249  pop     rsi
0x14001824a  pop     rbx
0x14001824b  pop     rbp
0x14001824c  retn
```
