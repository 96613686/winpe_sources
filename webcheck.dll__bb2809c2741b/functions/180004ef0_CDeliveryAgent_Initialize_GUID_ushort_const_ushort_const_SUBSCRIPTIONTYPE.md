# CDeliveryAgent::Initialize(_GUID *,ushort const *,ushort const *,SUBSCRIPTIONTYPE)

- ea: `0x180004ef0`
- end: `0x180004fe7`
- name: `?Initialize@CDeliveryAgent@@UEAAJPEAU_GUID@@PEBG1W4SUBSCRIPTIONTYPE@@@Z`
- size: `247`
- prototype: `int(CDeliveryAgent *__hidden this, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, enum SUBSCRIPTIONTYPE)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180003950`
- `0x180004ef0`
- `0x18000bb8c`
- `0x18000c740`
- `0x180019ae0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180004f18`
- `KERNEL32!LocalAlloc` at `0x180004f18`

## pseudocode

```c
__int64 __fastcall CDeliveryAgent::Initialize(
        CDeliveryAgent *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        enum SUBSCRIPTIONTYPE a5)
{
  HLOCAL v9; // rax
  struct _GUID v10; // xmm0
  struct OOEBuf *v11; // rdx
  unsigned int DefaultOOEBuf; // ebx
  struct ISubscriptionItem *v14; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v15; // [rsp+50h] [rbp+8h] BYREF

  v9 = LocalAlloc(0x40u, 0x1590u);
  *((_QWORD *)this + 2) = v9;
  if ( v9 )
  {
    v14 = 0;
    if ( (int)SubscriptionItemFromCookie(0, a2, &v14) < 0 )
    {
      DefaultOOEBuf = GetDefaultOOEBuf(*((struct OOEBuf **)this + 2), a5);
      StringCchCopyW((unsigned __int16 *)(*((_QWORD *)this + 2) + 556LL), 0x825u, a3);
      StringCchCopyW((unsigned __int16 *)(*((_QWORD *)this + 2) + 4726LL), 0x105u, a4);
      *(struct _GUID *)(*((_QWORD *)this + 2) + 116LL) = *a2;
    }
    else
    {
      v10 = *a2;
      v11 = (struct OOEBuf *)*((_QWORD *)this + 2);
      v15 = 0;
      *(struct _GUID *)((char *)this + 56) = v10;
      DefaultOOEBuf = LoadWithCookie(0, v11, &v15, a2);
      ((void (__fastcall *)(struct ISubscriptionItem *))v14->lpVtbl->Release)(v14);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return DefaultOOEBuf;
}

```

## disassembly

```asm
0x180004ef0  mov     [rsp+arg_8], rbx
0x180004ef5  mov     [rsp+arg_10], rbp
0x180004efa  push    rsi
0x180004efb  push    rdi
0x180004efc  push    r14
0x180004efe  sub     rsp, 30h
0x180004f02  mov     rsi, rdx
0x180004f05  mov     rdi, rcx
0x180004f08  mov     edx, 1590h; uBytes
0x180004f0d  mov     ecx, 40h ; '@'; uFlags
0x180004f12  mov     rbp, r9
0x180004f15  mov     r14, r8
0x180004f18  call    cs:__imp_LocalAlloc
0x180004f1e  mov     [rdi+10h], rax
0x180004f22  test    rax, rax
0x180004f25  jz      loc_180004FCD
0x180004f2b  lea     r8, [rsp+48h+var_28]; struct ISubscriptionItem **
0x180004f30  mov     [rsp+48h+var_28], 0
0x180004f39  mov     rdx, rsi; struct _GUID *
0x180004f3c  xor     ecx, ecx; int
0x180004f3e  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x180004f43  test    eax, eax
0x180004f45  js      short loc_180004F7F
0x180004f47  movups  xmm0, xmmword ptr [rsi]
0x180004f4a  mov     rdx, [rdi+10h]; struct OOEBuf *
0x180004f4e  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180004f53  mov     r9, rsi; struct _GUID *
0x180004f56  mov     [rsp+48h+arg_0], 0
0x180004f5e  xor     ecx, ecx; psz2
0x180004f60  movdqu  xmmword ptr [rdi+38h], xmm0
0x180004f65  call    ?LoadWithCookie@@YAJPEBGPEAUOOEBuf@@PEAKPEAU_GUID@@@Z; LoadWithCookie(ushort const *,OOEBuf *,ulong *,_GUID *)
0x180004f6a  mov     rcx, [rsp+48h+var_28]
0x180004f6f  mov     ebx, eax
0x180004f71  mov     rdx, [rcx]
0x180004f74  mov     rax, [rdx+10h]
0x180004f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f7d  jmp     short loc_180004FD2
0x180004f7f  mov     edx, [rsp+48h+arg_20]; enum SUBSCRIPTIONTYPE
0x180004f83  mov     rcx, [rdi+10h]; struct OOEBuf *
0x180004f87  call    ?GetDefaultOOEBuf@@YAJPEAUOOEBuf@@W4SUBSCRIPTIONTYPE@@@Z; GetDefaultOOEBuf(OOEBuf *,SUBSCRIPTIONTYPE)
0x180004f8c  mov     rcx, [rdi+10h]
0x180004f90  mov     r8, r14; unsigned __int16 *
0x180004f93  add     rcx, 22Ch; unsigned __int16 *
0x180004f9a  mov     edx, 825h; unsigned __int64
0x180004f9f  mov     ebx, eax
0x180004fa1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004fa6  mov     rcx, [rdi+10h]
0x180004faa  mov     r8, rbp; unsigned __int16 *
0x180004fad  add     rcx, 1276h; unsigned __int16 *
0x180004fb4  mov     edx, 105h; unsigned __int64
0x180004fb9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004fbe  mov     r11, [rdi+10h]
0x180004fc2  movups  xmm0, xmmword ptr [rsi]
0x180004fc5  movdqu  xmmword ptr [r11+74h], xmm0
0x180004fcb  jmp     short loc_180004FD2
0x180004fcd  mov     ebx, 8007000Eh
0x180004fd2  mov     rbp, [rsp+48h+arg_10]
0x180004fd7  mov     eax, ebx
0x180004fd9  mov     rbx, [rsp+48h+arg_8]
0x180004fde  add     rsp, 30h
0x180004fe2  pop     r14
0x180004fe4  pop     rdi
0x180004fe5  pop     rsi
0x180004fe6  retn
```
