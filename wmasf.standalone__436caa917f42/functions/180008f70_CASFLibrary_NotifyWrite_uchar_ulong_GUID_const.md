# CASFLibrary::NotifyWrite(uchar *,ulong,_GUID const &)

- ea: `0x180008f70`
- end: `0x180009060`
- name: `?NotifyWrite@CASFLibrary@@UEAAJPEAEKAEBU_GUID@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(CASFLibrary *__hidden this, unsigned __int8 *, unsigned int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180007910`
- `0x180008f70`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFLibrary::NotifyWrite(
        CASFLibrary *this,
        unsigned __int8 *a2,
        unsigned int a3,
        const struct _GUID *a4)
{
  __int64 result; // rax
  unsigned int v9; // edi
  unsigned int i; // ebx
  __int64 v11; // rax
  _BYTE v12[8]; // [rsp+30h] [rbp-58h] BYREF
  struct IWMSCriticalSection *v13; // [rsp+38h] [rbp-50h] BYREF

  v13 = 0;
  result = (*(__int64 (__fastcall **)(char *, struct IWMSCriticalSection **))(*((_QWORD *)this - 1) + 24LL))(
             (char *)this - 8,
             &v13);
  if ( (int)result >= 0 )
  {
    CAutoCritSec::CAutoCritSec((CAutoCritSec *)v12, v13);
    if ( v13 )
    {
      (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
    }
    v9 = *((_DWORD *)this + 128);
    for ( i = 0; i < v9; ++i )
    {
      if ( CTDynArray<IASFReadWriteTracker *,20>::operator[]((__int64)this + 296, i) )
      {
        v11 = CTDynArray<IASFReadWriteTracker *,20>::operator[]((__int64)this + 296, i);
        (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, const struct _GUID *))(*(_QWORD *)v11 + 80LL))(
          v11,
          a2,
          a3,
          a4);
      }
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v12);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008f70  push    rbx
0x180008f72  push    rbp
0x180008f73  push    rsi
0x180008f74  push    rdi
0x180008f75  push    r14
0x180008f77  push    r15
0x180008f79  sub     rsp, 58h
0x180008f7d  mov     rax, cs:__security_cookie
0x180008f84  xor     rax, rsp
0x180008f87  mov     [rsp+88h+var_48], rax
0x180008f8c  mov     rsi, rcx
0x180008f8f  mov     [rsp+88h+var_50], 0
0x180008f98  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180008f9c  mov     rbp, rdx
0x180008f9f  lea     rdx, [rsp+88h+var_50]
0x180008fa4  mov     r15, r9
0x180008fa7  mov     r14d, r8d
0x180008faa  mov     rax, [rcx]
0x180008fad  mov     rax, [rax+18h]
0x180008fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fb6  test    eax, eax
0x180008fb8  js      loc_180009046
0x180008fbe  mov     rdx, [rsp+88h+var_50]; struct IWMSCriticalSection *
0x180008fc3  lea     rcx, [rsp+88h+var_58]; this
0x180008fc8  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180008fcd  mov     rcx, [rsp+88h+var_50]
0x180008fd2  test    rcx, rcx
0x180008fd5  jz      short loc_180008FEC
0x180008fd7  mov     rax, [rcx]
0x180008fda  mov     rax, [rax+10h]
0x180008fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fe3  mov     [rsp+88h+var_50], 0
0x180008fec  mov     edi, [rsi+200h]
0x180008ff2  xor     ebx, ebx
0x180008ff4  test    edi, edi
0x180008ff6  jz      short loc_18000903A
0x180008ff8  mov     edx, ebx
0x180008ffa  lea     rcx, [rsi+128h]
0x180009001  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180009006  test    rax, rax
0x180009009  jz      short loc_180009034
0x18000900b  mov     edx, ebx
0x18000900d  lea     rcx, [rsi+128h]
0x180009014  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180009019  mov     r10, rax
0x18000901c  mov     r9, r15
0x18000901f  mov     r8d, r14d
0x180009022  mov     rdx, rbp
0x180009025  mov     rcx, [rax]
0x180009028  mov     rax, [rcx+50h]
0x18000902c  mov     rcx, r10
0x18000902f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009034  inc     ebx
0x180009036  cmp     ebx, edi
0x180009038  jb      short loc_180008FF8
0x18000903a  lea     rcx, [rsp+88h+var_58]; this
0x18000903f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180009044  xor     eax, eax
0x180009046  mov     rcx, [rsp+88h+var_48]
0x18000904b  xor     rcx, rsp; StackCookie
0x18000904e  call    __security_check_cookie
0x180009053  add     rsp, 58h
0x180009057  pop     r15
0x180009059  pop     r14
0x18000905b  pop     rdi
0x18000905c  pop     rsi
0x18000905d  pop     rbp
0x18000905e  pop     rbx
0x18000905f  retn
```
