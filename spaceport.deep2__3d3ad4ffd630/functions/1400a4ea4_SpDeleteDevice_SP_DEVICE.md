# SpDeleteDevice(SP_DEVICE *)

- ea: `0x1400a4ea4`
- end: `0x1400a5208`
- name: `?SpDeleteDevice@@YAXPEAVSP_DEVICE@@@Z`
- size: `868`
- prototype: `void __fastcall(struct SP_DEVICE *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140032038`
- `0x14009d884`
- `0x14009d910`
- `0x1400a47b8`
- `0x1400b8430`

## callees

- `0x140019500`
- `0x14001e4a0`
- `0x14002b054`
- `0x140031d80`
- `0x140067fc0`
- `0x140068000`
- `0x1400684c0`
- `0x1400a4ea4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400a4fbf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a5025`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a508b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a4fbf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a5025`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a508b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5129`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5129`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4f6f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a51a0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4f6f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a51a0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a517e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a517e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a518f`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a518f`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5149`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5149`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a4f07`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a4f07`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a4f4b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a4f4b`
- `ntoskrnl!IoDeleteDevice` at `0x1400a51cc`
- `ntoskrnl!IoDeleteDevice` at `0x1400a51cc`
- `ntoskrnl!IofCompleteRequest` at `0x1400a5116`
- `ntoskrnl!IofCompleteRequest` at `0x1400a5116`

## pseudocode

```c
void __fastcall SpDeleteDevice(struct SP_DEVICE *a1)
{
  struct _DEVICE_OBJECT *v1; // rbp
  struct SP_DEVICE **v3; // rdx
  struct SP_DEVICE **v4; // rax
  char *DeviceExtension; // rcx
  char v6; // si
  void *v7; // rcx
  unsigned int v8; // edx
  unsigned int i; // edi
  SP_WORKITEM *v10; // rcx
  unsigned int j; // edi
  SP_WORKITEM *v12; // rcx
  unsigned int k; // edi
  SP_WORKITEM *v14; // rcx
  struct SP_DEVICE *v15; // rdi
  struct SP_DEVICE *v16; // rcx
  __int64 v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  IRP *v20; // rcx
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-148h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-138h] BYREF
  wchar_t pszDest[128]; // [rsp+50h] [rbp-128h] BYREF

  v1 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 20);
  GuidString = 0;
  memset(pszDest, 0, sizeof(pszDest));
  DestinationString = 0;
  ExAcquirePushLockExclusiveEx((char *)WPP_MAIN_CB.DeviceExtension + 320, 0);
  v3 = (struct SP_DEVICE **)*((_QWORD *)a1 + 1);
  if ( v3[1] != (struct SP_DEVICE *)((char *)a1 + 8)
    || (v4 = (struct SP_DEVICE **)*((_QWORD *)a1 + 2), *v4 != (struct SP_DEVICE *)((char *)a1 + 8)) )
  {
LABEL_33:
    __fastfail(3u);
  }
  DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
  v6 = 0;
  *v4 = (struct SP_DEVICE *)v3;
  v3[1] = (struct SP_DEVICE *)v4;
  ExReleasePushLockExclusiveEx(DeviceExtension + 320, 0);
  v7 = (void *)*((_QWORD *)a1 + 394);
  if ( v7 )
    SC_ENV_ALLOCATOR::operator delete[](v7);
  RtlFreeUnicodeString((PUNICODE_STRING)a1 + 195);
  if ( *((_QWORD *)a1 + 298) )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 36); ++i )
      KeWaitForSingleObject((PVOID)(*((_QWORD *)a1 + 298) + 176LL + 208LL * i), Executive, 0, 0, 0);
    v10 = (SP_WORKITEM *)*((_QWORD *)a1 + 298);
    if ( v10 )
      SP_WORKITEM::`vector deleting destructor'(v10, v8);
  }
  if ( *((_QWORD *)a1 + 299) )
  {
    for ( j = 0; j < *((_DWORD *)a1 + 36); ++j )
      KeWaitForSingleObject((PVOID)(*((_QWORD *)a1 + 299) + 176LL + 208LL * j), Executive, 0, 0, 0);
    v12 = (SP_WORKITEM *)*((_QWORD *)a1 + 299);
    if ( v12 )
      SP_WORKITEM::`vector deleting destructor'(v12, v8);
  }
  if ( *((_QWORD *)a1 + 300) )
  {
    for ( k = 0; k < *((_DWORD *)a1 + 36); ++k )
      KeWaitForSingleObject((PVOID)(*((_QWORD *)a1 + 300) + 176LL + 208LL * k), Executive, 0, 0, 0);
    v14 = (SP_WORKITEM *)*((_QWORD *)a1 + 300);
    if ( v14 )
      SP_WORKITEM::`vector deleting destructor'(v14, v8);
  }
  v15 = (struct SP_DEVICE *)((char *)a1 + 3088);
  v16 = (struct SP_DEVICE *)*((_QWORD *)a1 + 386);
  if ( v16 == (struct SP_DEVICE *)((char *)a1 + 3088) )
    goto LABEL_36;
  do
  {
    v17 = _InterlockedExchange64((volatile __int64 *)v16 - 8, 0);
    v16 = *(struct SP_DEVICE **)v16;
    if ( !v17 )
      v6 = 1;
  }
  while ( v16 != v15 );
  if ( !v6 )
  {
LABEL_36:
    while ( 1 )
    {
      v18 = *(_QWORD **)v15;
      if ( *(struct SP_DEVICE **)v15 == v15 )
        break;
      if ( (struct SP_DEVICE *)v18[1] != v15 )
        goto LABEL_33;
      v19 = (_QWORD *)*v18;
      if ( *(_QWORD **)(*v18 + 8LL) != v18 )
        goto LABEL_33;
      *(_QWORD *)v15 = v19;
      v20 = (IRP *)(v18 - 21);
      v19[1] = v15;
      v20->IoStatus.Status = -1073741130;
      IofCompleteRequest(v20, 0);
      ObfDereferenceObject(*((PVOID *)a1 + 20));
    }
  }
  if ( *((_BYTE *)a1 + 168) == 6 && RtlStringFromGUID((const GUID *const)((char *)a1 + 40), &GuidString) >= 0 )
  {
    RtlStringCbPrintfW(pszDest, 0x100u, L"\\DosDevices\\Global\\Space#%wZ", &GuidString);
    RtlInitUnicodeString(&DestinationString, pszDest);
    IoDeleteSymbolicLink(&DestinationString);
    RtlFreeUnicodeString(&GuidString);
  }
  SpUnInitializeLimiterContext((void **)a1 + 411);
  (**(void (__fastcall ***)(struct SP_DEVICE *, __int64))a1)(a1, 1);
  IoDeleteDevice(v1);
}

```

## disassembly

```asm
0x1400a4ea4  mov     [rsp+arg_8], rbx
0x1400a4ea9  mov     [rsp+arg_10], rbp
0x1400a4eae  push    rsi
0x1400a4eaf  push    rdi
0x1400a4eb0  push    r15
0x1400a4eb2  sub     rsp, 160h
0x1400a4eb9  mov     rax, cs:__security_cookie
0x1400a4ec0  xor     rax, rsp
0x1400a4ec3  mov     [rsp+178h+var_28], rax
0x1400a4ecb  mov     rbp, [rcx+0A0h]
0x1400a4ed2  mov     rbx, rcx
0x1400a4ed5  xorps   xmm0, xmm0
0x1400a4ed8  lea     rcx, [rsp+178h+pszDest]; void *
0x1400a4edd  xor     edx, edx; Val
0x1400a4edf  mov     r8d, 100h; Size
0x1400a4ee5  movups  xmmword ptr [rsp+178h+GuidString.Length], xmm0
0x1400a4eea  call    memset
0x1400a4eef  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4ef6  xorps   xmm0, xmm0
0x1400a4ef9  add     rcx, 140h
0x1400a4f00  xor     edx, edx
0x1400a4f02  movups  xmmword ptr [rsp+178h+DestinationString.Length], xmm0
0x1400a4f07  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400a4f0e  nop     dword ptr [rax+rax+00h]
0x1400a4f13  lea     rcx, [rbx+8]
0x1400a4f17  mov     rdx, [rcx]
0x1400a4f1a  cmp     [rdx+8], rcx
0x1400a4f1e  jnz     loc_1400A5201
0x1400a4f24  mov     rax, [rcx+8]
0x1400a4f28  cmp     [rax], rcx
0x1400a4f2b  jnz     loc_1400A5201
0x1400a4f31  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4f38  xor     sil, sil
0x1400a4f3b  mov     [rax], rdx
0x1400a4f3e  add     rcx, 140h
0x1400a4f45  mov     [rdx+8], rax
0x1400a4f49  xor     edx, edx
0x1400a4f4b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400a4f52  nop     dword ptr [rax+rax+00h]
0x1400a4f57  mov     rcx, [rbx+0C50h]; void *
0x1400a4f5e  test    rcx, rcx
0x1400a4f61  jz      short loc_1400A4F68
0x1400a4f63  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a4f68  lea     rcx, [rbx+0C30h]; UnicodeString
0x1400a4f6f  call    cs:__imp_RtlFreeUnicodeString
0x1400a4f76  nop     dword ptr [rax+rax+00h]
0x1400a4f7b  cmp     qword ptr [rbx+950h], 0
0x1400a4f83  mov     r15d, 1
0x1400a4f89  jz      short loc_1400A4FE7
0x1400a4f8b  xor     edi, edi
0x1400a4f8d  cmp     [rbx+90h], edi
0x1400a4f93  jbe     short loc_1400A4FD6
0x1400a4f95  mov     eax, edi
0x1400a4f97  xor     r9d, r9d; Alertable
0x1400a4f9a  imul    rcx, rax, 0D0h
0x1400a4fa1  mov     rax, [rbx+950h]
0x1400a4fa8  xor     r8d, r8d; WaitMode
0x1400a4fab  add     rax, 0B0h
0x1400a4fb1  mov     [rsp+178h+Timeout], 0; Timeout
0x1400a4fba  add     rcx, rax; Object
0x1400a4fbd  xor     edx, edx; WaitReason
0x1400a4fbf  call    cs:__imp_KeWaitForSingleObject
0x1400a4fc6  nop     dword ptr [rax+rax+00h]
0x1400a4fcb  add     edi, r15d
0x1400a4fce  cmp     edi, [rbx+90h]
0x1400a4fd4  jb      short loc_1400A4F95
0x1400a4fd6  mov     rcx, [rbx+950h]; this
0x1400a4fdd  test    rcx, rcx
0x1400a4fe0  jz      short loc_1400A4FE7
0x1400a4fe2  call    ??_ESP_WORKITEM@@QEAAPEAXI@Z; SP_WORKITEM::`vector deleting destructor'(uint)
0x1400a4fe7  cmp     qword ptr [rbx+958h], 0
0x1400a4fef  jz      short loc_1400A504D
0x1400a4ff1  xor     edi, edi
0x1400a4ff3  cmp     [rbx+90h], edi
0x1400a4ff9  jbe     short loc_1400A503C
0x1400a4ffb  mov     eax, edi
0x1400a4ffd  xor     r9d, r9d; Alertable
0x1400a5000  imul    rcx, rax, 0D0h
0x1400a5007  mov     rax, [rbx+958h]
0x1400a500e  xor     r8d, r8d; WaitMode
0x1400a5011  add     rax, 0B0h
0x1400a5017  mov     [rsp+178h+Timeout], 0; Timeout
0x1400a5020  add     rcx, rax; Object
0x1400a5023  xor     edx, edx; WaitReason
0x1400a5025  call    cs:__imp_KeWaitForSingleObject
0x1400a502c  nop     dword ptr [rax+rax+00h]
0x1400a5031  add     edi, r15d
0x1400a5034  cmp     edi, [rbx+90h]
0x1400a503a  jb      short loc_1400A4FFB
0x1400a503c  mov     rcx, [rbx+958h]; this
0x1400a5043  test    rcx, rcx
0x1400a5046  jz      short loc_1400A504D
0x1400a5048  call    ??_ESP_WORKITEM@@QEAAPEAXI@Z; SP_WORKITEM::`vector deleting destructor'(uint)
0x1400a504d  cmp     qword ptr [rbx+960h], 0
0x1400a5055  jz      short loc_1400A50B3
0x1400a5057  xor     edi, edi
0x1400a5059  cmp     [rbx+90h], edi
0x1400a505f  jbe     short loc_1400A50A2
0x1400a5061  mov     eax, edi
0x1400a5063  xor     r9d, r9d; Alertable
0x1400a5066  imul    rcx, rax, 0D0h
0x1400a506d  mov     rax, [rbx+960h]
0x1400a5074  xor     r8d, r8d; WaitMode
0x1400a5077  add     rax, 0B0h
0x1400a507d  mov     [rsp+178h+Timeout], 0; Timeout
0x1400a5086  add     rcx, rax; Object
0x1400a5089  xor     edx, edx; WaitReason
0x1400a508b  call    cs:__imp_KeWaitForSingleObject
0x1400a5092  nop     dword ptr [rax+rax+00h]
0x1400a5097  add     edi, r15d
0x1400a509a  cmp     edi, [rbx+90h]
0x1400a50a0  jb      short loc_1400A5061
0x1400a50a2  mov     rcx, [rbx+960h]; this
0x1400a50a9  test    rcx, rcx
0x1400a50ac  jz      short loc_1400A50B3
0x1400a50ae  call    ??_ESP_WORKITEM@@QEAAPEAXI@Z; SP_WORKITEM::`vector deleting destructor'(uint)
0x1400a50b3  lea     rdi, [rbx+0C10h]
0x1400a50ba  mov     rcx, [rdi]
0x1400a50bd  cmp     rcx, rdi
0x1400a50c0  jz      short loc_1400A50E0
0x1400a50c2  xor     eax, eax
0x1400a50c4  movzx   esi, sil
0x1400a50c8  xchg    rax, [rcx-40h]
0x1400a50cc  mov     rcx, [rcx]
0x1400a50cf  test    rax, rax
0x1400a50d2  cmovz   esi, r15d
0x1400a50d6  cmp     rcx, rdi
0x1400a50d9  jnz     short loc_1400A50C2
0x1400a50db  test    sil, sil
0x1400a50de  jnz     short loc_1400A5137
0x1400a50e0  mov     rcx, [rdi]
0x1400a50e3  cmp     rcx, rdi
0x1400a50e6  jz      short loc_1400A5137
0x1400a50e8  cmp     [rcx+8], rdi
0x1400a50ec  jnz     loc_1400A5201
0x1400a50f2  mov     rax, [rcx]
0x1400a50f5  cmp     [rax+8], rcx
0x1400a50f9  jnz     loc_1400A5201
0x1400a50ff  mov     [rdi], rax
0x1400a5102  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1400a5109  mov     [rax+8], rdi
0x1400a510d  xor     edx, edx; PriorityBoost
0x1400a510f  mov     dword ptr [rcx+30h], 0C00002B6h
0x1400a5116  call    cs:__imp_IofCompleteRequest
0x1400a511d  nop     dword ptr [rax+rax+00h]
0x1400a5122  mov     rcx, [rbx+0A0h]; Object
0x1400a5129  call    cs:__imp_ObfDereferenceObject
0x1400a5130  nop     dword ptr [rax+rax+00h]
0x1400a5135  jmp     short loc_1400A50E0
0x1400a5137  cmp     byte ptr [rbx+0A8h], 6
0x1400a513e  jnz     short loc_1400A51AC
0x1400a5140  lea     rcx, [rbx+28h]; Guid
0x1400a5144  lea     rdx, [rsp+178h+GuidString]; GuidString
0x1400a5149  call    cs:__imp_RtlStringFromGUID
0x1400a5150  nop     dword ptr [rax+rax+00h]
0x1400a5155  test    eax, eax
0x1400a5157  js      short loc_1400A51AC
0x1400a5159  lea     r9, [rsp+178h+GuidString]
0x1400a515e  mov     edx, 100h; cbDest
0x1400a5163  lea     r8, aDosdevicesGlob; "\\DosDevices\\Global\\Space#%wZ"
0x1400a516a  lea     rcx, [rsp+178h+pszDest]; pszDest
0x1400a516f  call    RtlStringCbPrintfW
0x1400a5174  lea     rdx, [rsp+178h+pszDest]; SourceString
0x1400a5179  lea     rcx, [rsp+178h+DestinationString]; DestinationString
0x1400a517e  call    cs:__imp_RtlInitUnicodeString
0x1400a5185  nop     dword ptr [rax+rax+00h]
0x1400a518a  lea     rcx, [rsp+178h+DestinationString]; SymbolicLinkName
0x1400a518f  call    cs:__imp_IoDeleteSymbolicLink
0x1400a5196  nop     dword ptr [rax+rax+00h]
0x1400a519b  lea     rcx, [rsp+178h+GuidString]; UnicodeString
0x1400a51a0  call    cs:__imp_RtlFreeUnicodeString
0x1400a51a7  nop     dword ptr [rax+rax+00h]
0x1400a51ac  lea     rcx, [rbx+0CD8h]; void **
0x1400a51b3  call    ?SpUnInitializeLimiterContext@@YAXPEAPEAX@Z; SpUnInitializeLimiterContext(void * *)
0x1400a51b8  mov     rax, [rbx]
0x1400a51bb  mov     edx, r15d
0x1400a51be  mov     rcx, rbx
0x1400a51c1  mov     rax, [rax]
0x1400a51c4  call    _guard_dispatch_icall
0x1400a51c9  mov     rcx, rbp; DeviceObject
0x1400a51cc  call    cs:__imp_IoDeleteDevice
0x1400a51d3  nop     dword ptr [rax+rax+00h]
0x1400a51d8  mov     rcx, [rsp+178h+var_28]
0x1400a51e0  xor     rcx, rsp; StackCookie
0x1400a51e3  call    __security_check_cookie
0x1400a51e8  lea     r11, [rsp+178h+var_18]
0x1400a51f0  mov     rbx, [r11+28h]
0x1400a51f4  mov     rbp, [r11+30h]
0x1400a51f8  mov     rsp, r11
0x1400a51fb  pop     r15
0x1400a51fd  pop     rdi
0x1400a51fe  pop     rsi
0x1400a51ff  retn
0x1400a5201  mov     ecx, 3
0x1400a5206  int     29h; Win8: RtlFailFast(ecx)
```
