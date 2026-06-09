# CASFBaseIndexMaker::NotifyReadDataUnit(uchar *,ulong,ushort,_ASF_DATA_DESCRIPTOR *)

- ea: `0x18003dae0`
- end: `0x18003db85`
- name: `?NotifyReadDataUnit@CASFBaseIndexMaker@@UEAAJPEAEKGPEAU_ASF_DATA_DESCRIPTOR@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(CASFBaseIndexMaker *__hidden this, unsigned __int8 *, unsigned int, unsigned __int16, struct _ASF_DATA_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18003dae0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFBaseIndexMaker::NotifyReadDataUnit(
        struct IWMSCriticalSection **this,
        unsigned __int8 *a2,
        unsigned int a3,
        __int16 a4,
        struct _ASF_DATA_DESCRIPTOR *a5)
{
  __int16 v10; // [rsp+20h] [rbp-38h]
  char v11; // [rsp+60h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v11, this[1625]);
  if ( *((_DWORD *)this + 3) || !*((_DWORD *)this + 4) )
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
    return 1;
  }
  else
  {
    if ( *((_DWORD *)this + 17) == 1 )
    {
      v10 = a4;
      (*((void (__fastcall **)(char *, unsigned __int8 *, _QWORD, GUID *, __int16, struct _ASF_DATA_DESCRIPTOR *))*(this - 1)
       + 13))(
        (char *)this - 8,
        a2,
        a3,
        &CLSID_ASFDataUnitData,
        v10,
        a5);
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
    return 0;
  }
}

```

## disassembly

```asm
0x18003dae0  mov     [rsp+arg_8], rbx
0x18003dae5  mov     [rsp+arg_10], rbp
0x18003daea  push    rsi
0x18003daeb  push    rdi
0x18003daec  push    r14
0x18003daee  sub     rsp, 40h
0x18003daf2  mov     r14, rdx
0x18003daf5  mov     rbx, rcx
0x18003daf8  mov     rdx, [rcx+32C8h]; struct IWMSCriticalSection *
0x18003daff  movzx   esi, r9w
0x18003db03  lea     rcx, [rsp+58h+arg_0]; this
0x18003db08  mov     ebp, r8d
0x18003db0b  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18003db10  cmp     dword ptr [rbx+0Ch], 0
0x18003db14  jnz     short loc_18003DB63
0x18003db16  cmp     dword ptr [rbx+10h], 0
0x18003db1a  jz      short loc_18003DB63
0x18003db1c  cmp     dword ptr [rbx+44h], 1
0x18003db20  jnz     short loc_18003DB55
0x18003db22  mov     rax, [rbx-8]
0x18003db26  lea     r9, CLSID_ASFDataUnitData
0x18003db2d  mov     r8d, ebp
0x18003db30  lea     rcx, [rbx-8]
0x18003db34  mov     rdx, r14
0x18003db37  mov     r10, [rax+68h]
0x18003db3b  mov     rax, [rsp+58h+arg_20]
0x18003db43  mov     [rsp+58h+var_30], rax
0x18003db48  mov     rax, r10
0x18003db4b  mov     [rsp+58h+var_38], si
0x18003db50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db55  lea     rcx, [rsp+58h+arg_0]; this
0x18003db5a  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18003db5f  xor     eax, eax
0x18003db61  jmp     short loc_18003DB72
0x18003db63  lea     rcx, [rsp+58h+arg_0]; this
0x18003db68  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18003db6d  mov     eax, 1
0x18003db72  mov     rbx, [rsp+58h+arg_8]
0x18003db77  mov     rbp, [rsp+58h+arg_10]
0x18003db7c  add     rsp, 40h
0x18003db80  pop     r14
0x18003db82  pop     rdi
0x18003db83  pop     rsi
0x18003db84  retn
```
