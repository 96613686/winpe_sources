# CGpWmpEncoder::CreateNewFrame(IWICBitmapFrameEncode * *,IPropertyBag2 * *)

- ea: `0x18003a3e0`
- end: `0x18003a464`
- name: `?CreateNewFrame@CGpWmpEncoder@@UEAAJPEAPEAUIWICBitmapFrameEncode@@PEAPEAUIPropertyBag2@@@Z`
- size: `132`
- prototype: `int(CGpWmpEncoder *__hidden this, struct IWICBitmapFrameEncode **, struct IPropertyBag2 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002db34`
- `0x1800322d0`
- `0x18003a3e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a40b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a40b`

## pseudocode

```c
__int64 __fastcall CGpWmpEncoder::CreateNewFrame(
        CGpWmpEncoder *this,
        struct IWICBitmapFrameEncode **a2,
        struct IPropertyBag2 **a3)
{
  char *v3; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  int NewFrameInternal; // ebx
  char *v10; // [rsp+30h] [rbp+8h] BYREF

  v3 = (char *)this - 56;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v10 = v3;
  if ( LOBYTE(v5[1].DebugInfo) )
    EnterCriticalSection(v5);
  if ( a2 )
  {
    if ( *((_DWORD *)this + 13) )
    {
      NewFrameInternal = -2003292287;
    }
    else
    {
      NewFrameInternal = CGpWmpEncoder::CreateNewFrameInternal((CGpWmpEncoder *)((char *)this - 80), a2, a3, 0);
      if ( NewFrameInternal >= 0 )
        ++*((_DWORD *)this + 13);
    }
  }
  else
  {
    NewFrameInternal = -2147024809;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v10);
  return (unsigned int)NewFrameInternal;
}

```

## disassembly

```asm
0x18003a3e0  mov     [rsp+arg_8], rbx
0x18003a3e5  mov     [rsp+arg_10], rsi
0x18003a3ea  push    rdi
0x18003a3eb  sub     rsp, 20h
0x18003a3ef  lea     rax, [rcx-38h]
0x18003a3f3  mov     rdi, rcx
0x18003a3f6  lea     rcx, [rax+8]; lpCriticalSection
0x18003a3fa  mov     [rsp+28h+arg_0], rax
0x18003a3ff  cmp     byte ptr [rcx+28h], 0
0x18003a403  mov     rsi, r8
0x18003a406  mov     rbx, rdx
0x18003a409  jz      short loc_18003A411
0x18003a40b  call    cs:__imp_EnterCriticalSection
0x18003a411  test    rbx, rbx
0x18003a414  jnz     short loc_18003A41D
0x18003a416  mov     ebx, 80070057h
0x18003a41b  jmp     short loc_18003A448
0x18003a41d  lea     rcx, [rdi-50h]; this
0x18003a421  cmp     dword ptr [rcx+84h], 1
0x18003a428  jb      short loc_18003A431
0x18003a42a  mov     ebx, 88982F81h
0x18003a42f  jmp     short loc_18003A448
0x18003a431  xor     r9d, r9d; int
0x18003a434  mov     r8, rsi; struct IPropertyBag2 **
0x18003a437  mov     rdx, rbx; struct IWICBitmapFrameEncode **
0x18003a43a  call    ?CreateNewFrameInternal@CGpWmpEncoder@@UEAAJPEAPEAUIWICBitmapFrameEncode@@PEAPEAUIPropertyBag2@@H@Z; CGpWmpEncoder::CreateNewFrameInternal(IWICBitmapFrameEncode * *,IPropertyBag2 * *,int)
0x18003a43f  mov     ebx, eax
0x18003a441  test    eax, eax
0x18003a443  js      short loc_18003A448
0x18003a445  inc     dword ptr [rdi+34h]
0x18003a448  lea     rcx, [rsp+28h+arg_0]
0x18003a44d  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003a452  mov     rsi, [rsp+28h+arg_10]
0x18003a457  mov     eax, ebx
0x18003a459  mov     rbx, [rsp+28h+arg_8]
0x18003a45e  add     rsp, 20h
0x18003a462  pop     rdi
0x18003a463  retn
```
