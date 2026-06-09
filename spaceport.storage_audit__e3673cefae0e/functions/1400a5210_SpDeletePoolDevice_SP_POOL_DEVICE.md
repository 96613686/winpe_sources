# SpDeletePoolDevice(SP_POOL_DEVICE *)

- ea: `0x1400a5210`
- end: `0x1400a5301`
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
- `0x1400a1bd8`

## callees

- `0x140019500`
- `0x140032d74`
- `0x140067fc0`
- `0x1400684c0`
- `0x1400a5210`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a52b7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a52b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a5295`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a5295`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a52a6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a52a6`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5260`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5260`
- `ntoskrnl!IoDeleteDevice` at `0x1400a52d3`
- `ntoskrnl!IoDeleteDevice` at `0x1400a52d3`

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
0x1400a5210  mov     [rsp+arg_8], rbx
0x1400a5215  push    rdi
0x1400a5216  sub     rsp, 150h
0x1400a521d  mov     rax, cs:__security_cookie
0x1400a5224  xor     rax, rsp
0x1400a5227  mov     [rsp+158h+var_18], rax
0x1400a522f  mov     rdi, [rcx]
0x1400a5232  mov     rbx, rcx
0x1400a5235  xorps   xmm0, xmm0
0x1400a5238  lea     rcx, [rsp+158h+pszDest]; void *
0x1400a523d  xor     edx, edx; Val
0x1400a523f  mov     r8d, 100h; Size
0x1400a5245  movups  xmmword ptr [rsp+158h+GuidString.Length], xmm0
0x1400a524a  call    memset
0x1400a524f  xorps   xmm0, xmm0
0x1400a5252  lea     rcx, [rbx+8]; Guid
0x1400a5256  lea     rdx, [rsp+158h+GuidString]; GuidString
0x1400a525b  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm0
0x1400a5260  call    cs:__imp_RtlStringFromGUID
0x1400a5267  nop     dword ptr [rax+rax+00h]
0x1400a526c  test    eax, eax
0x1400a526e  js      short loc_1400A52C3
0x1400a5270  lea     r9, [rsp+158h+GuidString]
0x1400a5275  mov     edx, 100h; cbDest
0x1400a527a  lea     r8, aDosdevicesGlob_0; "\\DosDevices\\Global\\Pool#%wZ"
0x1400a5281  lea     rcx, [rsp+158h+pszDest]; pszDest
0x1400a5286  call    RtlStringCbPrintfW
0x1400a528b  lea     rdx, [rsp+158h+pszDest]; SourceString
0x1400a5290  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x1400a5295  call    cs:__imp_RtlInitUnicodeString
0x1400a529c  nop     dword ptr [rax+rax+00h]
0x1400a52a1  lea     rcx, [rsp+158h+DestinationString]; SymbolicLinkName
0x1400a52a6  call    cs:__imp_IoDeleteSymbolicLink
0x1400a52ad  nop     dword ptr [rax+rax+00h]
0x1400a52b2  lea     rcx, [rsp+158h+GuidString]; UnicodeString
0x1400a52b7  call    cs:__imp_RtlFreeUnicodeString
0x1400a52be  nop     dword ptr [rax+rax+00h]
0x1400a52c3  test    rbx, rbx
0x1400a52c6  jz      short loc_1400A52D0
0x1400a52c8  mov     rcx, rbx; this
0x1400a52cb  call    ??1SP_POOL_DEVICE@@QEAA@XZ; SP_POOL_DEVICE::~SP_POOL_DEVICE(void)
0x1400a52d0  mov     rcx, rdi; DeviceObject
0x1400a52d3  call    cs:__imp_IoDeleteDevice
0x1400a52da  nop     dword ptr [rax+rax+00h]
0x1400a52df  mov     rcx, [rsp+158h+var_18]
0x1400a52e7  xor     rcx, rsp; StackCookie
0x1400a52ea  call    __security_check_cookie
0x1400a52ef  mov     rbx, [rsp+158h+arg_8]
0x1400a52f7  add     rsp, 150h
0x1400a52fe  pop     rdi
0x1400a52ff  retn
```
