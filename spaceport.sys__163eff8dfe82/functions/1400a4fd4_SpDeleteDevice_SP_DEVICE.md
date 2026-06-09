# SpDeleteDevice(SP_DEVICE *)

- ea: `0x1400a4fd4`
- end: `0x1400a5338`
- name: `?SpDeleteDevice@@YAXPEAVSP_DEVICE@@@Z`
- size: `868`
- prototype: `void __fastcall(struct SP_DEVICE *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1400320a8`
- `0x14009d8a4`
- `0x14009d930`
- `0x1400a48e8`
- `0x1400b85d0`

## callees

- `0x140019500`
- `0x14001e4a0`
- `0x14002b054`
- `0x140031df0`
- `0x140068110`
- `0x140068150`
- `0x140068600`
- `0x1400a4fd4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400a50ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a5155`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a51bb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a50ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a5155`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a51bb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5259`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5259`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a509f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a52d0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a509f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a52d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a52ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a52ae`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a52bf`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a52bf`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5279`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5279`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a5037`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a5037`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a507b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a507b`
- `ntoskrnl!IoDeleteDevice` at `0x1400a52fc`
- `ntoskrnl!IoDeleteDevice` at `0x1400a52fc`
- `ntoskrnl!IofCompleteRequest` at `0x1400a5246`
- `ntoskrnl!IofCompleteRequest` at `0x1400a5246`

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
0x1400a4fd4  mov     [rsp+arg_8], rbx
0x1400a4fd9  mov     [rsp+arg_10], rbp
0x1400a4fde  push    rsi
0x1400a4fdf  push    rdi
0x1400a4fe0  push    r15
0x1400a4fe2  sub     rsp, 160h
0x1400a4fe9  mov     rax, cs:__security_cookie
0x1400a4ff0  xor     rax, rsp
0x1400a4ff3  mov     [rsp+178h+var_28], rax
0x1400a4ffb  mov     rbp, [rcx+0A0h]
0x1400a5002  mov     rbx, rcx
0x1400a5005  xorps   xmm0, xmm0
0x1400a5008  lea     rcx, [rsp+178h+pszDest]; void *
0x1400a500d  xor     edx, edx; Val
0x1400a500f  mov     r8d, 100h; Size
0x1400a5015  movups  xmmword ptr [rsp+178h+GuidString.Length], xmm0
0x1400a501a  call    memset
0x1400a501f  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a5026  xorps   xmm0, xmm0
0x1400a5029  add     rcx, 140h
0x1400a5030  xor     edx, edx
0x1400a5032  movups  xmmword ptr [rsp+178h+DestinationString.Length], xmm0
0x1400a5037  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400a503e  nop     dword ptr [rax+rax+00h]
0x1400a5043  lea     rcx, [rbx+8]
0x1400a5047  mov     rdx, [rcx]
0x1400a504a  cmp     [rdx+8], rcx
0x1400a504e  jnz     loc_1400A5331
0x1400a5054  mov     rax, [rcx+8]
0x1400a5058  cmp     [rax], rcx
0x1400a505b  jnz     loc_1400A5331
0x1400a5061  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a5068  xor     sil, sil
0x1400a506b  mov     [rax], rdx
0x1400a506e  add     rcx, 140h
0x1400a5075  mov     [rdx+8], rax
0x1400a5079  xor     edx, edx
0x1400a507b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400a5082  nop     dword ptr [rax+rax+00h]
0x1400a5087  mov     rcx, [rbx+0C50h]; void *
0x1400a508e  test    rcx, rcx
0x1400a5091  jz      short loc_1400A5098
0x1400a5093  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a5098  lea     rcx, [rbx+0C30h]; UnicodeString
0x1400a509f  call    cs:__imp_RtlFreeUnicodeString
0x1400a50a6  nop     dword ptr [rax+rax+00h]
0x1400a50ab  cmp     qword ptr [rbx+950h], 0
0x1400a50b3  mov     r15d, 1
0x1400a50b9  jz      short loc_1400A5117
0x1400a50bb  xor     edi, edi
0x1400a50bd  cmp     [rbx+90h], edi
0x1400a50c3  jbe     short loc_1400A5106
0x1400a50c5  mov     eax, edi
0x1400a50c7  xor     r9d, r9d; Alertable
0x1400a50ca  imul    rcx, rax, 0D0h
0x1400a50d1  mov     rax, [rbx+950h]
0x1400a50d8  xor     r8d, r8d; WaitMode
0x1400a50db  add     rax, 0B0h
0x1400a50e1  mov     [rsp+178h+Timeout], 0; Timeout
0x1400a50ea  add     rcx, rax; Object
0x1400a50ed  xor     edx, edx; WaitReason
0x1400a50ef  call    cs:__imp_KeWaitForSingleObject
0x1400a50f6  nop     dword ptr [rax+rax+00h]
0x1400a50fb  add     edi, r15d
0x1400a50fe  cmp     edi, [rbx+90h]
0x1400a5104  jb      short loc_1400A50C5
0x1400a5106  mov     rcx, [rbx+950h]; this
0x1400a510d  test    rcx, rcx
0x1400a5110  jz      short loc_1400A5117
0x1400a5112  call    ??_ESP_WORKITEM@@QEAAPEAXI@Z; SP_WORKITEM::`vector deleting destructor'(uint)
0x1400a5117  cmp     qword ptr [rbx+958h], 0
0x1400a511f  jz      short loc_1400A517D
0x1400a5121  xor     edi, edi
0x1400a5123  cmp     [rbx+90h], edi
0x1400a5129  jbe     short loc_1400A516C
0x1400a512b  mov     eax, edi
0x1400a512d  xor     r9d, r9d; Alertable
0x1400a5130  imul    rcx, rax, 0D0h
0x1400a5137  mov     rax, [rbx+958h]
0x1400a513e  xor     r8d, r8d; WaitMode
0x1400a5141  add     rax, 0B0h
0x1400a5147  mov     [rsp+178h+Timeout], 0; Timeout
0x1400a5150  add     rcx, rax; Object
0x1400a5153  xor     edx, edx; WaitReason
0x1400a5155  call    cs:__imp_KeWaitForSingleObject
0x1400a515c  nop     dword ptr [rax+rax+00h]
0x1400a5161  add     edi, r15d
0x1400a5164  cmp     edi, [rbx+90h]
0x1400a516a  jb      short loc_1400A512B
0x1400a516c  mov     rcx, [rbx+958h]; this
0x1400a5173  test    rcx, rcx
0x1400a5176  jz      short loc_1400A517D
0x1400a5178  call    ??_ESP_WORKITEM@@QEAAPEAXI@Z; SP_WORKITEM::`vector deleting destructor'(uint)
0x1400a517d  cmp     qword ptr [rbx+960h], 0
0x1400a5185  jz      short loc_1400A51E3
0x1400a5187  xor     edi, edi
0x1400a5189  cmp     [rbx+90h], edi
0x1400a518f  jbe     short loc_1400A51D2
0x1400a5191  mov     eax, edi
0x1400a5193  xor     r9d, r9d; Alertable
0x1400a5196  imul    rcx, rax, 0D0h
0x1400a519d  mov     rax, [rbx+960h]
0x1400a51a4  xor     r8d, r8d; WaitMode
0x1400a51a7  add     rax, 0B0h
0x1400a51ad  mov     [rsp+178h+Timeout], 0; Timeout
0x1400a51b6  add     rcx, rax; Object
0x1400a51b9  xor     edx, edx; WaitReason
0x1400a51bb  call    cs:__imp_KeWaitForSingleObject
0x1400a51c2  nop     dword ptr [rax+rax+00h]
0x1400a51c7  add     edi, r15d
0x1400a51ca  cmp     edi, [rbx+90h]
0x1400a51d0  jb      short loc_1400A5191
0x1400a51d2  mov     rcx, [rbx+960h]; this
0x1400a51d9  test    rcx, rcx
0x1400a51dc  jz      short loc_1400A51E3
0x1400a51de  call    ??_ESP_WORKITEM@@QEAAPEAXI@Z; SP_WORKITEM::`vector deleting destructor'(uint)
0x1400a51e3  lea     rdi, [rbx+0C10h]
0x1400a51ea  mov     rcx, [rdi]
0x1400a51ed  cmp     rcx, rdi
0x1400a51f0  jz      short loc_1400A5210
0x1400a51f2  xor     eax, eax
0x1400a51f4  movzx   esi, sil
0x1400a51f8  xchg    rax, [rcx-40h]
0x1400a51fc  mov     rcx, [rcx]
0x1400a51ff  test    rax, rax
0x1400a5202  cmovz   esi, r15d
0x1400a5206  cmp     rcx, rdi
0x1400a5209  jnz     short loc_1400A51F2
0x1400a520b  test    sil, sil
0x1400a520e  jnz     short loc_1400A5267
0x1400a5210  mov     rcx, [rdi]
0x1400a5213  cmp     rcx, rdi
0x1400a5216  jz      short loc_1400A5267
0x1400a5218  cmp     [rcx+8], rdi
0x1400a521c  jnz     loc_1400A5331
0x1400a5222  mov     rax, [rcx]
0x1400a5225  cmp     [rax+8], rcx
0x1400a5229  jnz     loc_1400A5331
0x1400a522f  mov     [rdi], rax
0x1400a5232  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1400a5239  mov     [rax+8], rdi
0x1400a523d  xor     edx, edx; PriorityBoost
0x1400a523f  mov     dword ptr [rcx+30h], 0C00002B6h
0x1400a5246  call    cs:__imp_IofCompleteRequest
0x1400a524d  nop     dword ptr [rax+rax+00h]
0x1400a5252  mov     rcx, [rbx+0A0h]; Object
0x1400a5259  call    cs:__imp_ObfDereferenceObject
0x1400a5260  nop     dword ptr [rax+rax+00h]
0x1400a5265  jmp     short loc_1400A5210
0x1400a5267  cmp     byte ptr [rbx+0A8h], 6
0x1400a526e  jnz     short loc_1400A52DC
0x1400a5270  lea     rcx, [rbx+28h]; Guid
0x1400a5274  lea     rdx, [rsp+178h+GuidString]; GuidString
0x1400a5279  call    cs:__imp_RtlStringFromGUID
0x1400a5280  nop     dword ptr [rax+rax+00h]
0x1400a5285  test    eax, eax
0x1400a5287  js      short loc_1400A52DC
0x1400a5289  lea     r9, [rsp+178h+GuidString]
0x1400a528e  mov     edx, 100h; cbDest
0x1400a5293  lea     r8, aDosdevicesGlob; "\\DosDevices\\Global\\Space#%wZ"
0x1400a529a  lea     rcx, [rsp+178h+pszDest]; pszDest
0x1400a529f  call    RtlStringCbPrintfW
0x1400a52a4  lea     rdx, [rsp+178h+pszDest]; SourceString
0x1400a52a9  lea     rcx, [rsp+178h+DestinationString]; DestinationString
0x1400a52ae  call    cs:__imp_RtlInitUnicodeString
0x1400a52b5  nop     dword ptr [rax+rax+00h]
0x1400a52ba  lea     rcx, [rsp+178h+DestinationString]; SymbolicLinkName
0x1400a52bf  call    cs:__imp_IoDeleteSymbolicLink
0x1400a52c6  nop     dword ptr [rax+rax+00h]
0x1400a52cb  lea     rcx, [rsp+178h+GuidString]; UnicodeString
0x1400a52d0  call    cs:__imp_RtlFreeUnicodeString
0x1400a52d7  nop     dword ptr [rax+rax+00h]
0x1400a52dc  lea     rcx, [rbx+0CD8h]; void **
0x1400a52e3  call    ?SpUnInitializeLimiterContext@@YAXPEAPEAX@Z; SpUnInitializeLimiterContext(void * *)
0x1400a52e8  mov     rax, [rbx]
0x1400a52eb  mov     edx, r15d
0x1400a52ee  mov     rcx, rbx
0x1400a52f1  mov     rax, [rax]
0x1400a52f4  call    _guard_dispatch_icall
0x1400a52f9  mov     rcx, rbp; DeviceObject
0x1400a52fc  call    cs:__imp_IoDeleteDevice
0x1400a5303  nop     dword ptr [rax+rax+00h]
0x1400a5308  mov     rcx, [rsp+178h+var_28]
0x1400a5310  xor     rcx, rsp; StackCookie
0x1400a5313  call    __security_check_cookie
0x1400a5318  lea     r11, [rsp+178h+var_18]
0x1400a5320  mov     rbx, [r11+28h]
0x1400a5324  mov     rbp, [r11+30h]
0x1400a5328  mov     rsp, r11
0x1400a532b  pop     r15
0x1400a532d  pop     rdi
0x1400a532e  pop     rsi
0x1400a532f  retn
0x1400a5331  mov     ecx, 3
0x1400a5336  int     29h; Win8: RtlFailFast(ecx)
```
