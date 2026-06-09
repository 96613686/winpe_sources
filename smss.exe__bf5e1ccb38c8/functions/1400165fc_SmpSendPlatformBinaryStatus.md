# SmpSendPlatformBinaryStatus

- ea: `0x1400165fc`
- end: `0x1400168b0`
- name: `SmpSendPlatformBinaryStatus`
- size: `692`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c638`
- `0x1400143b0`

## callees

- `0x140001008`
- `0x1400165fc`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1400166d1`
- `ntdll!NtOpenFile` at `0x1400166d1`
- `ntdll!NtDeviceIoControlFile` at `0x14001675f`
- `ntdll!NtDeviceIoControlFile` at `0x14001675f`
- `ntdll!NtClose` at `0x14001676f`
- `ntdll!NtClose` at `0x14001676f`
- `ntdll!RtlAllocateHeap` at `0x140016673`
- `ntdll!RtlAllocateHeap` at `0x140016673`
- `ntdll!RtlFreeHeap` at `0x14001678c`
- `ntdll!RtlFreeHeap` at `0x14001678c`
- `ntdll!EtwEventWrite` at `0x1400167d6`
- `ntdll!EtwEventWrite` at `0x1400167d6`

## pseudocode

```c
__int64 __fastcall SmpSendPlatformBinaryStatus(int a1, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  char *InputBuffer; // rbx
  int v8; // r8d
  int v9; // r9d
  int v10; // ecx
  __int128 *v11; // r9
  __int64 *v12; // rdx
  __int64 v13; // r8
  __int64 result; // rax
  __int16 *v15; // rdx
  int ShareAccess; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  void *FileHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  __int128 v22; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v23[32]; // [rsp+C0h] [rbp-40h] BYREF
  int *v24; // [rsp+E0h] [rbp-20h]
  __int64 v25; // [rsp+E8h] [rbp-18h]
  __int64 *v26; // [rsp+F0h] [rbp-10h]
  __int64 v27; // [rsp+F8h] [rbp-8h]
  _DWORD *v28; // [rsp+100h] [rbp+0h]
  __int64 v29; // [rsp+108h] [rbp+8h]
  __int64 v30; // [rsp+110h] [rbp+10h]
  _DWORD v31[2]; // [rsp+118h] [rbp+18h] BYREF
  int v32; // [rsp+180h] [rbp+80h] BYREF

  v32 = a1;
  FileHandle = 0;
  v22 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a1 )
    a2 = 0;
  IoStatusBlock = 0;
  InputBuffer = (char *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 8u, 0x34u);
  if ( InputBuffer )
  {
    ObjectAttributes.ObjectName = (PUNICODE_STRING)L"8:";
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenFile(&FileHandle, 0x120003u, &ObjectAttributes, &IoStatusBlock, 2u, 0x60u) >= 0 )
    {
      *((_DWORD *)InputBuffer + 5) = 1;
      *((_DWORD *)InputBuffer + 7) = 1;
      *(_DWORD *)InputBuffer = 1130980673;
      *((_DWORD *)InputBuffer + 1) = 1396854879;
      *((_DWORD *)InputBuffer + 2) = 52;
      *((_DWORD *)InputBuffer + 3) = 4;
      *((_DWORD *)InputBuffer + 4) = 0x40000;
      *((_DWORD *)InputBuffer + 6) = 0x40000;
      *((_DWORD *)InputBuffer + 8) = 0x40000;
      *((_DWORD *)InputBuffer + 9) = v32;
      *((_DWORD *)InputBuffer + 10) = 524290;
      *(_QWORD *)(InputBuffer + 44) = a2;
      NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x32C000u, InputBuffer, 0x34u, 0, 0);
    }
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( InputBuffer )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, InputBuffer);
  v10 = SmpTraceHandle;
  if ( SmpTraceHandle )
  {
    if ( v32 )
    {
      *((_QWORD *)&v22 + 1) = 4;
      *(_QWORD *)&v22 = &v32;
      v11 = &v22;
      v13 = 1;
      v12 = SmssEvt_PlatformBinaryExecutionFailed;
    }
    else
    {
      v11 = 0;
      v12 = SmssEvt_PlatformBinaryExecuted;
      v13 = 0;
    }
    EtwEventWrite(SmpTraceHandle, v12, v13, v11);
  }
  result = (unsigned int)dword_14002EE08;
  if ( a4 )
  {
    if ( (unsigned int)dword_14002EE08 <= 5 )
      return result;
    v15 = (__int16 *)&byte_14002A337;
    v17 = v32;
    v24 = &v17;
    v26 = &v19;
    v28 = v31;
    v30 = *((_QWORD *)a4 + 1);
    v31[0] = *a4;
    ShareAccess = 6;
    v29 = 2;
    v31[1] = 0;
  }
  else
  {
    if ( (unsigned int)dword_14002EE08 <= 5 )
      return result;
    v15 = &word_14002A306;
    v17 = v32;
    v24 = &v17;
    v26 = &v19;
    ShareAccess = 4;
  }
  v25 = 4;
  v19 = a3;
  v27 = 8;
  return tlgWriteTransfer_EtwEventWriteTransfer(v10, (_DWORD)v15, v8, v9, ShareAccess, (__int64)v23);
}

```

## disassembly

```asm
0x1400165fc  mov     [rsp-8+arg_0], ecx
0x140016600  push    rbp
0x140016601  push    rbx
0x140016602  push    rsi
0x140016603  push    rdi
0x140016604  push    r12
0x140016606  push    r13
0x140016608  push    r14
0x14001660a  push    r15
0x14001660c  lea     rbp, [rsp-38h]
0x140016611  sub     rsp, 138h
0x140016618  mov     rax, cs:__security_cookie
0x14001661f  xor     rax, rsp
0x140016622  mov     [rbp+70h+var_50], rax
0x140016626  xorps   xmm0, xmm0
0x140016629  xor     eax, eax
0x14001662b  movups  xmmword ptr [rsp+170h+ObjectAttributes.ObjectName], xmm0
0x140016630  xor     r15d, r15d
0x140016633  mov     r14, rdx
0x140016636  test    ecx, ecx
0x140016638  mov     [rsp+170h+FileHandle], r15
0x14001663d  movups  xmmword ptr [rbp+70h+ObjectAttributes+1Ch], xmm0
0x140016641  lea     r13d, [rax+8]
0x140016645  mov     rsi, r8
0x140016648  movups  [rbp+70h+var_C8], xmm0
0x14001664c  lea     r8d, [rax+34h]; Size
0x140016650  mov     edx, r13d; Flags
0x140016653  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm0
0x140016658  mov     rdi, r9
0x14001665b  cmovnz  r14, r15
0x14001665f  xorps   xmm1, xmm1
0x140016662  movups  xmmword ptr [rbp+70h+IoStatusBlock], xmm1
0x140016666  mov     rcx, gs:60h
0x14001666f  mov     rcx, [rcx+30h]; HeapHandle
0x140016673  call    cs:__imp_RtlAllocateHeap
0x140016679  lea     r12d, [r15+4]
0x14001667d  mov     rbx, rax
0x140016680  test    rax, rax
0x140016683  jz      loc_140016765
0x140016689  lea     rax, SmpPlatformBinarySymbolicLink; "8:"
0x140016690  mov     [rsp+170h+OpenOptions], 60h ; '`'; OpenOptions
0x140016698  xorps   xmm0, xmm0
0x14001669b  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x1400166a0  lea     r9, [rbp+70h+IoStatusBlock]; IoStatusBlock
0x1400166a4  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1400166ac  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1400166b1  mov     [rsp+170h+ObjectAttributes.RootDirectory], r15
0x1400166b6  mov     edx, 120003h; DesiredAccess
0x1400166bb  mov     [rbp+70h+ObjectAttributes.Attributes], r15d
0x1400166bf  lea     rcx, [rsp+170h+FileHandle]; FileHandle
0x1400166c4  mov     [rsp+170h+ShareAccess], 2; ShareAccess
0x1400166cc  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400166d1  call    cs:__imp_NtOpenFile
0x1400166d7  test    eax, eax
0x1400166d9  js      loc_140016765
0x1400166df  mov     [rsp+170h+OutputBufferLength], r15d; OutputBufferLength
0x1400166e4  lea     ecx, [r15+1]
0x1400166e8  mov     [rsp+170h+OutputBuffer], r15; OutputBuffer
0x1400166ed  xor     r9d, r9d; ApcContext
0x1400166f0  mov     [rbx+14h], ecx
0x1400166f3  xor     r8d, r8d; ApcRoutine
0x1400166f6  mov     [rbx+1Ch], ecx
0x1400166f9  xor     edx, edx; Event
0x1400166fb  mov     dword ptr [rbx], 43696541h
0x140016701  mov     dword ptr [rbx+4], 5342505Fh
0x140016708  mov     dword ptr [rbx+8], 34h ; '4'
0x14001670f  mov     [rbx+0Ch], r12d
0x140016713  mov     dword ptr [rbx+10h], 40000h
0x14001671a  mov     dword ptr [rbx+18h], 40000h
0x140016721  mov     dword ptr [rbx+20h], 40000h
0x140016728  mov     eax, [rbp+70h+arg_0]
0x14001672e  mov     [rbx+24h], eax
0x140016731  lea     rax, [rbp+70h+IoStatusBlock]
0x140016735  mov     [rsp+170h+InputBufferLength], 34h ; '4'; InputBufferLength
0x14001673d  mov     dword ptr [rbx+28h], 80002h
0x140016744  mov     [rbx+2Ch], r14
0x140016748  mov     rcx, [rsp+170h+FileHandle]; FileHandle
0x14001674d  mov     [rsp+170h+InputBuffer], rbx; InputBuffer
0x140016752  mov     [rsp+170h+OpenOptions], 32C000h; IoControlCode
0x14001675a  mov     qword ptr [rsp+170h+ShareAccess], rax; IoStatusBlock
0x14001675f  call    cs:__imp_NtDeviceIoControlFile
0x140016765  mov     rcx, [rsp+170h+FileHandle]; Handle
0x14001676a  test    rcx, rcx
0x14001676d  jz      short loc_140016775
0x14001676f  call    cs:__imp_NtClose
0x140016775  test    rbx, rbx
0x140016778  jz      short loc_140016792
0x14001677a  mov     rcx, gs:60h
0x140016783  mov     r8, rbx; BaseAddress
0x140016786  xor     edx, edx; Flags
0x140016788  mov     rcx, [rcx+30h]; HeapHandle
0x14001678c  call    cs:__imp_RtlFreeHeap
0x140016792  mov     rcx, cs:SmpTraceHandle
0x140016799  test    rcx, rcx
0x14001679c  jz      short loc_1400167DC
0x14001679e  cmp     [rbp+70h+arg_0], r15d
0x1400167a5  jnz     short loc_1400167B6
0x1400167a7  xor     r9d, r9d
0x1400167aa  lea     rdx, SmssEvt_PlatformBinaryExecuted
0x1400167b1  xor     r8d, r8d
0x1400167b4  jmp     short loc_1400167D6
0x1400167b6  lea     rax, [rbp+70h+arg_0]
0x1400167bd  mov     qword ptr [rbp+70h+var_C8+8], r12
0x1400167c1  mov     qword ptr [rbp+70h+var_C8], rax
0x1400167c5  lea     r9, [rbp+70h+var_C8]
0x1400167c9  mov     r8d, 1
0x1400167cf  lea     rdx, SmssEvt_PlatformBinaryExecutionFailed
0x1400167d6  call    cs:__imp_EtwEventWrite
0x1400167dc  mov     eax, cs:dword_14002EE08
0x1400167e2  test    rdi, rdi
0x1400167e5  jz      short loc_140016848
0x1400167e7  cmp     eax, 5
0x1400167ea  jbe     loc_140016890
0x1400167f0  mov     eax, [rbp+70h+arg_0]
0x1400167f6  lea     rdx, byte_14002A337
0x1400167fd  mov     [rsp+170h+var_120], eax
0x140016801  lea     rax, [rsp+170h+var_120]
0x140016806  mov     [rbp+70h+var_90], rax
0x14001680a  lea     rax, [rsp+170h+var_110]
0x14001680f  mov     [rbp+70h+var_80], rax
0x140016813  lea     rax, [rbp+70h+var_58]
0x140016817  mov     [rbp+70h+var_70], rax
0x14001681b  mov     rax, [rdi+8]
0x14001681f  mov     [rbp+70h+var_60], rax
0x140016823  movzx   eax, word ptr [rdi]
0x140016826  mov     [rbp+70h+var_58], eax
0x140016829  lea     rax, [rbp+70h+var_B0]
0x14001682d  mov     qword ptr [rsp+170h+OpenOptions], rax
0x140016832  mov     [rsp+170h+ShareAccess], 6
0x14001683a  mov     [rbp+70h+var_68], 2
0x140016842  mov     [rbp+70h+var_54], r15d
0x140016846  jmp     short loc_14001687E
0x140016848  cmp     eax, 5
0x14001684b  jbe     short loc_140016890
0x14001684d  mov     eax, [rbp+70h+arg_0]
0x140016853  lea     rdx, word_14002A306
0x14001685a  mov     [rsp+170h+var_120], eax
0x14001685e  lea     rax, [rsp+170h+var_120]
0x140016863  mov     [rbp+70h+var_90], rax
0x140016867  lea     rax, [rsp+170h+var_110]
0x14001686c  mov     [rbp+70h+var_80], rax
0x140016870  lea     rax, [rbp+70h+var_B0]
0x140016874  mov     qword ptr [rsp+170h+OpenOptions], rax
0x140016879  mov     [rsp+170h+ShareAccess], r12d
0x14001687e  mov     [rbp+70h+var_88], r12
0x140016882  mov     [rsp+170h+var_110], rsi
0x140016887  mov     [rbp+70h+var_78], r13
0x14001688b  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x140016890  mov     rcx, [rbp+70h+var_50]
0x140016894  xor     rcx, rsp; StackCookie
0x140016897  call    __security_check_cookie
0x14001689c  add     rsp, 138h
0x1400168a3  pop     r15
0x1400168a5  pop     r14
0x1400168a7  pop     r13
0x1400168a9  pop     r12
0x1400168ab  pop     rdi
0x1400168ac  pop     rsi
0x1400168ad  pop     rbx
0x1400168ae  pop     rbp
0x1400168af  retn
```
