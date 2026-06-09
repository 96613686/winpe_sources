# SpDeletePoolDevice(SP_POOL_DEVICE *)

- ea: `0x1400a5340`
- end: `0x1400a5431`
- name: `?SpDeletePoolDevice@@YAXPEAVSP_POOL_DEVICE@@@Z`
- size: `241`
- prototype: `void __fastcall(struct SP_POOL_DEVICE *this)`
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x14008cbf8`
- `0x14008ce50`
- `0x140092fbc`
- `0x1400a1d08`

## callees

- `0x140019500`
- `0x140032e28`
- `0x140068110`
- `0x140068600`
- `0x1400a5340`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a53e7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a53e7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a53c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a53c5`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a53d6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a53d6`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5390`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5390`
- `ntoskrnl!IoDeleteDevice` at `0x1400a5403`
- `ntoskrnl!IoDeleteDevice` at `0x1400a5403`

## pseudocode

```c
void __fastcall SpDeletePoolDevice(struct SP_POOL_DEVICE *this)
{
  struct _DEVICE_OBJECT *v1; // rdi
  struct _UNICODE_STRING GuidString; // [rsp+20h] [rbp-138h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-128h] BYREF
  wchar_t pszDest[128]; // [rsp+40h] [rbp-118h] BYREF

  v1 = *(struct _DEVICE_OBJECT **)this;
  GuidString = 0;
  memset(pszDest, 0, sizeof(pszDest));
  DestinationString = 0;
  if ( RtlStringFromGUID((const GUID *const)((char *)this + 8), &GuidString) >= 0 )
  {
    RtlStringCbPrintfW(pszDest, 0x100u, L"\\DosDevices\\Global\\Pool#%wZ", &GuidString);
    RtlInitUnicodeString(&DestinationString, pszDest);
    IoDeleteSymbolicLink(&DestinationString);
    RtlFreeUnicodeString(&GuidString);
  }
  if ( this )
    SP_POOL_DEVICE::~SP_POOL_DEVICE(this);
  IoDeleteDevice(v1);
}

```

## disassembly

```asm
0x1400a5340  mov     [rsp+arg_8], rbx
0x1400a5345  push    rdi
0x1400a5346  sub     rsp, 150h
0x1400a534d  mov     rax, cs:__security_cookie
0x1400a5354  xor     rax, rsp
0x1400a5357  mov     [rsp+158h+var_18], rax
0x1400a535f  mov     rdi, [rcx]
0x1400a5362  mov     rbx, rcx
0x1400a5365  xorps   xmm0, xmm0
0x1400a5368  lea     rcx, [rsp+158h+pszDest]; void *
0x1400a536d  xor     edx, edx; Val
0x1400a536f  mov     r8d, 100h; Size
0x1400a5375  movups  xmmword ptr [rsp+158h+GuidString.Length], xmm0
0x1400a537a  call    memset
0x1400a537f  xorps   xmm0, xmm0
0x1400a5382  lea     rcx, [rbx+8]; Guid
0x1400a5386  lea     rdx, [rsp+158h+GuidString]; GuidString
0x1400a538b  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm0
0x1400a5390  call    cs:__imp_RtlStringFromGUID
0x1400a5397  nop     dword ptr [rax+rax+00h]
0x1400a539c  test    eax, eax
0x1400a539e  js      short loc_1400A53F3
0x1400a53a0  lea     r9, [rsp+158h+GuidString]
0x1400a53a5  mov     edx, 100h; cbDest
0x1400a53aa  lea     r8, aDosdevicesGlob_0; "\\DosDevices\\Global\\Pool#%wZ"
0x1400a53b1  lea     rcx, [rsp+158h+pszDest]; pszDest
0x1400a53b6  call    RtlStringCbPrintfW
0x1400a53bb  lea     rdx, [rsp+158h+pszDest]; SourceString
0x1400a53c0  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x1400a53c5  call    cs:__imp_RtlInitUnicodeString
0x1400a53cc  nop     dword ptr [rax+rax+00h]
0x1400a53d1  lea     rcx, [rsp+158h+DestinationString]; SymbolicLinkName
0x1400a53d6  call    cs:__imp_IoDeleteSymbolicLink
0x1400a53dd  nop     dword ptr [rax+rax+00h]
0x1400a53e2  lea     rcx, [rsp+158h+GuidString]; UnicodeString
0x1400a53e7  call    cs:__imp_RtlFreeUnicodeString
0x1400a53ee  nop     dword ptr [rax+rax+00h]
0x1400a53f3  test    rbx, rbx
0x1400a53f6  jz      short loc_1400A5400
0x1400a53f8  mov     rcx, rbx; this
0x1400a53fb  call    ??1SP_POOL_DEVICE@@QEAA@XZ; SP_POOL_DEVICE::~SP_POOL_DEVICE(void)
0x1400a5400  mov     rcx, rdi; DeviceObject
0x1400a5403  call    cs:__imp_IoDeleteDevice
0x1400a540a  nop     dword ptr [rax+rax+00h]
0x1400a540f  mov     rcx, [rsp+158h+var_18]
0x1400a5417  xor     rcx, rsp; StackCookie
0x1400a541a  call    __security_check_cookie
0x1400a541f  mov     rbx, [rsp+158h+arg_8]
0x1400a5427  add     rsp, 150h
0x1400a542e  pop     rdi
0x1400a542f  retn
```
