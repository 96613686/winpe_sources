# CASFLibrary::NotifyWriteDataUnit(uchar *,ulong,ushort,_ASF_DATA_DESCRIPTOR *)

- ea: `0x180009070`
- end: `0x180009173`
- name: `?NotifyWriteDataUnit@CASFLibrary@@UEAAJPEAEKGPEAU_ASF_DATA_DESCRIPTOR@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(CASFLibrary *__hidden this, unsigned __int8 *, unsigned int, unsigned __int16, struct _ASF_DATA_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180007910`
- `0x180009070`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFLibrary::NotifyWriteDataUnit(
        CASFLibrary *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int16 a4,
        struct _ASF_DATA_DESCRIPTOR *a5)
{
  __int64 result; // rax
  unsigned int v10; // edi
  unsigned int i; // ebx
  __int64 v12; // rax
  _BYTE v13[8]; // [rsp+30h] [rbp-58h] BYREF
  struct IWMSCriticalSection *v14; // [rsp+38h] [rbp-50h] BYREF

  v14 = 0;
  result = (*(__int64 (__fastcall **)(char *, struct IWMSCriticalSection **))(*((_QWORD *)this - 1) + 24LL))(
             (char *)this - 8,
             &v14);
  if ( (int)result >= 0 )
  {
    CAutoCritSec::CAutoCritSec((CAutoCritSec *)v13, v14);
    if ( v14 )
    {
      (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    v10 = *((_DWORD *)this + 128);
    for ( i = 0; i < v10; ++i )
    {
      if ( CTDynArray<IASFReadWriteTracker *,20>::operator[]((__int64)this + 296, i) )
      {
        v12 = CTDynArray<IASFReadWriteTracker *,20>::operator[]((__int64)this + 296, i);
        (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD, struct _ASF_DATA_DESCRIPTOR *))(*(_QWORD *)v12 + 96LL))(
          v12,
          a2,
          a3,
          a4,
          a5);
      }
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009070  push    rbx
0x180009072  push    rbp
0x180009073  push    rsi
0x180009074  push    rdi
0x180009075  push    r12
0x180009077  push    r14
0x180009079  push    r15
0x18000907b  sub     rsp, 50h
0x18000907f  mov     rax, cs:__security_cookie
0x180009086  xor     rax, rsp
0x180009089  mov     [rsp+88h+var_48], rax
0x18000908e  mov     r12, [rsp+88h+arg_20]
0x180009096  mov     rsi, rcx
0x180009099  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18000909d  mov     [rsp+88h+var_50], 0
0x1800090a6  mov     rbp, rdx
0x1800090a9  movzx   r15d, r9w
0x1800090ad  lea     rdx, [rsp+88h+var_50]
0x1800090b2  mov     r14d, r8d
0x1800090b5  mov     rax, [rcx]
0x1800090b8  mov     rax, [rax+18h]
0x1800090bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090c1  test    eax, eax
0x1800090c3  js      loc_180009157
0x1800090c9  mov     rdx, [rsp+88h+var_50]; struct IWMSCriticalSection *
0x1800090ce  lea     rcx, [rsp+88h+var_58]; this
0x1800090d3  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x1800090d8  mov     rcx, [rsp+88h+var_50]
0x1800090dd  test    rcx, rcx
0x1800090e0  jz      short loc_1800090F7
0x1800090e2  mov     rax, [rcx]
0x1800090e5  mov     rax, [rax+10h]
0x1800090e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ee  mov     [rsp+88h+var_50], 0
0x1800090f7  mov     edi, [rsi+200h]
0x1800090fd  xor     ebx, ebx
0x1800090ff  test    edi, edi
0x180009101  jz      short loc_18000914B
0x180009103  mov     edx, ebx
0x180009105  lea     rcx, [rsi+128h]
0x18000910c  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180009111  test    rax, rax
0x180009114  jz      short loc_180009145
0x180009116  mov     edx, ebx
0x180009118  lea     rcx, [rsi+128h]
0x18000911f  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180009124  mov     r10, rax
0x180009127  mov     [rsp+88h+var_68], r12
0x18000912c  movzx   r9d, r15w
0x180009130  mov     r8d, r14d
0x180009133  mov     rdx, rbp
0x180009136  mov     rcx, [rax]
0x180009139  mov     rax, [rcx+60h]
0x18000913d  mov     rcx, r10
0x180009140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009145  inc     ebx
0x180009147  cmp     ebx, edi
0x180009149  jb      short loc_180009103
0x18000914b  lea     rcx, [rsp+88h+var_58]; this
0x180009150  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180009155  xor     eax, eax
0x180009157  mov     rcx, [rsp+88h+var_48]
0x18000915c  xor     rcx, rsp; StackCookie
0x18000915f  call    __security_check_cookie
0x180009164  add     rsp, 50h
0x180009168  pop     r15
0x18000916a  pop     r14
0x18000916c  pop     r12
0x18000916e  pop     rdi
0x18000916f  pop     rsi
0x180009170  pop     rbp
0x180009171  pop     rbx
0x180009172  retn
```
