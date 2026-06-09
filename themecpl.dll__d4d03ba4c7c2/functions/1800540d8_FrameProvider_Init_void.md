# FrameProvider::Init(void)

- ea: `0x1800540d8`
- end: `0x180054184`
- name: `?Init@FrameProvider@@QEAAJXZ`
- size: `172`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180039470`

## callees

- `0x180051e9c`
- `0x180051ff4`
- `0x180052820`
- `0x180052954`
- `0x180052a7c`
- `0x1800540d8`

## import_xrefs

- `DUI70!InitProcessPriv` at `0x1800540fc`
- `DUI70!InitProcessPriv` at `0x1800540fc`
- `DUI70!UnInitProcessPriv` at `0x18005412c`
- `DUI70!UnInitProcessPriv` at `0x18005412c`
- `DUI70!InitThread` at `0x180054113`
- `DUI70!InitThread` at `0x180054113`

## pseudocode

```c
__int64 __fastcall FrameProvider::Init(FrameProvider *this, __int64 a2, __int64 a3)
{
  int inited; // ebx

  LOBYTE(a3) = 1;
  inited = InitProcessPriv(14, &_ImageBase, a3);
  if ( inited >= 0 )
  {
    inited = InitThread(2);
    if ( inited < 0 )
      UnInitProcessPriv(&_ImageBase);
  }
  *((_DWORD *)this + 154) = inited;
  if ( inited >= 0 )
  {
    inited = -2147467259;
    if ( (int)CNavigateButton::Register() >= 0
      && (int)CElementWithIUnknown::Register() >= 0
      && (int)DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Register() >= 0
      && (int)DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register() >= 0
      && (int)CFocusIndicator::Register() >= 0 )
    {
      return 0;
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800540d8  mov     [rsp+arg_0], rbx
0x1800540dd  push    rdi
0x1800540de  sub     rsp, 30h
0x1800540e2  mov     r9b, 1
0x1800540e5  mov     [rsp+38h+var_18], 1
0x1800540ea  mov     rdi, rcx
0x1800540ed  lea     rdx, __ImageBase
0x1800540f4  mov     r8b, r9b
0x1800540f7  mov     ecx, 0Eh
0x1800540fc  call    cs:__imp_InitProcessPriv
0x180054103  nop     dword ptr [rax+rax+00h]
0x180054108  mov     ebx, eax
0x18005410a  test    eax, eax
0x18005410c  js      short loc_180054138
0x18005410e  mov     ecx, 2
0x180054113  call    cs:__imp_InitThread
0x18005411a  nop     dword ptr [rax+rax+00h]
0x18005411f  mov     ebx, eax
0x180054121  test    eax, eax
0x180054123  jns     short loc_180054138
0x180054125  lea     rcx, __ImageBase
0x18005412c  call    cs:__imp_UnInitProcessPriv
0x180054133  nop     dword ptr [rax+rax+00h]
0x180054138  mov     [rdi+268h], ebx
0x18005413e  test    ebx, ebx
0x180054140  js      short loc_180054176
0x180054142  mov     ebx, 80004005h
0x180054147  call    ?Register@CNavigateButton@@SAJXZ; CNavigateButton::Register(void)
0x18005414c  test    eax, eax
0x18005414e  js      short loc_180054176
0x180054150  call    ?Register@CElementWithIUnknown@@SAJXZ; CElementWithIUnknown::Register(void)
0x180054155  test    eax, eax
0x180054157  js      short loc_180054176
0x180054159  call    ?Register@?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@SAJPEBGPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Register(ushort const *,DirectUI::PropertyInfo const * const *,uint)
0x18005415e  test    eax, eax
0x180054160  js      short loc_180054176
0x180054162  call    ?Register@?$ClassInfo@VCFrameModule@@VCElementWithSite@@V?$StandardCreator@VCFrameModule@@@DirectUI@@@DirectUI@@SAJPEBGPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register(ushort const *,DirectUI::PropertyInfo const * const *,uint)
0x180054167  test    eax, eax
0x180054169  js      short loc_180054176
0x18005416b  call    ?Register@CFocusIndicator@@SAJXZ; CFocusIndicator::Register(void)
0x180054170  test    eax, eax
0x180054172  js      short loc_180054176
0x180054174  xor     ebx, ebx
0x180054176  mov     eax, ebx
0x180054178  mov     rbx, [rsp+38h+arg_0]
0x18005417d  add     rsp, 30h
0x180054181  pop     rdi
0x180054182  retn
```
