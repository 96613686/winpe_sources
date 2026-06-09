# CASFBaseIndexMaker::NotifyRead(uchar *,ulong,_GUID const &)

- ea: `0x18003da20`
- end: `0x18003dad1`
- name: `?NotifyRead@CASFBaseIndexMaker@@UEAAJPEAEKAEBU_GUID@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CASFBaseIndexMaker *__hidden this, unsigned __int8 *, unsigned int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18003da20`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFBaseIndexMaker::NotifyRead(
        struct IWMSCriticalSection **this,
        unsigned __int8 *a2,
        unsigned int a3,
        const struct _GUID *a4)
{
  __int64 v8; // rax
  char v10; // [rsp+60h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v10, this[1625]);
  if ( *((_DWORD *)this + 3) || !*((_DWORD *)this + 4) )
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
    return 1;
  }
  else
  {
    v8 = *(_QWORD *)&CLSID_ASFDataUnitData.Data1 - *(_QWORD *)&a4->Data1;
    if ( *(_QWORD *)&CLSID_ASFDataUnitData.Data1 == *(_QWORD *)&a4->Data1 )
      v8 = *(_QWORD *)CLSID_ASFDataUnitData.Data4 - *(_QWORD *)a4->Data4;
    if ( !v8 && *((_DWORD *)this + 17) == 1 )
      (*((void (__fastcall **)(char *, unsigned __int8 *, _QWORD, const struct _GUID *, _WORD, _QWORD))*(this - 1) + 13))(
        (char *)this - 8,
        a2,
        a3,
        a4,
        0,
        0);
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
    return 0;
  }
}

```

## disassembly

```asm
0x18003da20  mov     [rsp+arg_8], rbx
0x18003da25  mov     [rsp+arg_10], rbp
0x18003da2a  push    rsi
0x18003da2b  push    rdi
0x18003da2c  push    r14
0x18003da2e  sub     rsp, 40h
0x18003da32  mov     r14, rdx
0x18003da35  mov     rbx, rcx
0x18003da38  mov     rdx, [rcx+32C8h]; struct IWMSCriticalSection *
0x18003da3f  mov     rdi, r9
0x18003da42  lea     rcx, [rsp+58h+arg_0]; this
0x18003da47  mov     ebp, r8d
0x18003da4a  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18003da4f  xor     ecx, ecx
0x18003da51  cmp     [rbx+0Ch], ecx
0x18003da54  jnz     short loc_18003DAAF
0x18003da56  cmp     [rbx+10h], ecx
0x18003da59  jz      short loc_18003DAAF
0x18003da5b  mov     rax, qword ptr cs:CLSID_ASFDataUnitData.Data1
0x18003da62  sub     rax, [rdi]
0x18003da65  jnz     short loc_18003DA72
0x18003da67  mov     rax, qword ptr cs:CLSID_ASFDataUnitData.Data4
0x18003da6e  sub     rax, [rdi+8]
0x18003da72  test    rax, rax
0x18003da75  jnz     short loc_18003DAA1
0x18003da77  cmp     dword ptr [rbx+44h], 1
0x18003da7b  jnz     short loc_18003DAA1
0x18003da7d  mov     rax, [rbx-8]
0x18003da81  mov     r9, rdi
0x18003da84  mov     [rsp+58h+var_30], rcx
0x18003da89  mov     r8d, ebp
0x18003da8c  mov     [rsp+58h+var_38], cx
0x18003da91  mov     rdx, r14
0x18003da94  lea     rcx, [rbx-8]
0x18003da98  mov     rax, [rax+68h]
0x18003da9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003daa1  lea     rcx, [rsp+58h+arg_0]; this
0x18003daa6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18003daab  xor     eax, eax
0x18003daad  jmp     short loc_18003DABE
0x18003daaf  lea     rcx, [rsp+58h+arg_0]; this
0x18003dab4  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18003dab9  mov     eax, 1
0x18003dabe  mov     rbx, [rsp+58h+arg_8]
0x18003dac3  mov     rbp, [rsp+58h+arg_10]
0x18003dac8  add     rsp, 40h
0x18003dacc  pop     r14
0x18003dace  pop     rdi
0x18003dacf  pop     rsi
0x18003dad0  retn
```
