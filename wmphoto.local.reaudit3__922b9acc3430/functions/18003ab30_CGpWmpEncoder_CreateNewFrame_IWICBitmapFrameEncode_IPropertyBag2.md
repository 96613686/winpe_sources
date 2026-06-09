# CGpWmpEncoder::CreateNewFrame(IWICBitmapFrameEncode * *,IPropertyBag2 * *)

- ea: `0x18003ab30`
- end: `0x18003abbb`
- name: `?CreateNewFrame@CGpWmpEncoder@@UEAAJPEAPEAUIWICBitmapFrameEncode@@PEAPEAUIPropertyBag2@@@Z`
- size: `139`
- prototype: `int(CGpWmpEncoder *__hidden this, struct IWICBitmapFrameEncode **, struct IPropertyBag2 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002de30`
- `0x1800327b0`
- `0x18003ab30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ab5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ab5b`

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
0x18003ab30  mov     [rsp+arg_8], rbx
0x18003ab35  mov     [rsp+arg_10], rsi
0x18003ab3a  push    rdi
0x18003ab3b  sub     rsp, 20h
0x18003ab3f  lea     rax, [rcx-38h]
0x18003ab43  mov     rdi, rcx
0x18003ab46  lea     rcx, [rax+8]; lpCriticalSection
0x18003ab4a  mov     [rsp+28h+arg_0], rax
0x18003ab4f  cmp     byte ptr [rcx+28h], 0
0x18003ab53  mov     rsi, r8
0x18003ab56  mov     rbx, rdx
0x18003ab59  jz      short loc_18003AB67
0x18003ab5b  call    cs:__imp_EnterCriticalSection
0x18003ab62  nop     dword ptr [rax+rax+00h]
0x18003ab67  test    rbx, rbx
0x18003ab6a  jnz     short loc_18003AB73
0x18003ab6c  mov     ebx, 80070057h
0x18003ab71  jmp     short loc_18003AB9E
0x18003ab73  lea     rcx, [rdi-50h]; this
0x18003ab77  cmp     dword ptr [rcx+84h], 1
0x18003ab7e  jb      short loc_18003AB87
0x18003ab80  mov     ebx, 88982F81h
0x18003ab85  jmp     short loc_18003AB9E
0x18003ab87  xor     r9d, r9d; int
0x18003ab8a  mov     r8, rsi; struct IPropertyBag2 **
0x18003ab8d  mov     rdx, rbx; struct IWICBitmapFrameEncode **
0x18003ab90  call    ?CreateNewFrameInternal@CGpWmpEncoder@@UEAAJPEAPEAUIWICBitmapFrameEncode@@PEAPEAUIPropertyBag2@@H@Z; CGpWmpEncoder::CreateNewFrameInternal(IWICBitmapFrameEncode * *,IPropertyBag2 * *,int)
0x18003ab95  mov     ebx, eax
0x18003ab97  test    eax, eax
0x18003ab99  js      short loc_18003AB9E
0x18003ab9b  inc     dword ptr [rdi+34h]
0x18003ab9e  lea     rcx, [rsp+28h+arg_0]
0x18003aba3  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003aba8  mov     rsi, [rsp+28h+arg_10]
0x18003abad  mov     eax, ebx
0x18003abaf  mov     rbx, [rsp+28h+arg_8]
0x18003abb4  add     rsp, 20h
0x18003abb8  pop     rdi
0x18003abb9  retn
```
