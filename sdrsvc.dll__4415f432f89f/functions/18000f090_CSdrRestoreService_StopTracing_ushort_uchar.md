# CSdrRestoreService::StopTracing(ushort *,uchar)

- ea: `0x18000f090`
- end: `0x18000f150`
- name: `?StopTracing@CSdrRestoreService@@UEAAJPEAGE@Z`
- size: `192`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned __int16 *, unsigned __int8)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000f090`
- `0x18001586c`
- `0x180015974`
- `0x18001698c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f0c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f110`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f0c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f110`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f0d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f130`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021ba9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021bcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f0d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f130`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021ba9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021bcb`

## string_xrefs

- `0x18000f0b0`: `CSdrRestoreService::StopTracing`

## pseudocode

```c
__int64 __fastcall CSdrRestoreService::StopTracing(RTL_SRWLOCK *this, unsigned __int16 *a2, unsigned __int8 a3)
{
  const WCHAR *Ptr; // rsi
  unsigned __int8 v6; // r8
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-68h] BYREF
  __int16 v10; // [rsp+24h] [rbp-64h]
  __int16 v11; // [rsp+26h] [rbp-62h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CSdrRestoreService::StopTracing", 134, 1);
  AcquireSRWLockExclusive(this + 7);
  Ptr = (const WCHAR *)this[5].Ptr;
  ReleaseSRWLockExclusive(this + 7);
  if ( Ptr )
  {
    v9 = 0;
    v10 = 153;
    SdStopTracing(Ptr, a3, v6);
  }
  else
  {
    v9 = -2147024809;
    v11 = 153;
  }
  AcquireSRWLockExclusive(this + 7);
  if ( LODWORD(this[6].Ptr) )
  {
    LODWORD(this[6].Ptr) = 0;
    *(_WORD *)this[5].Ptr = 0;
  }
  ReleaseSRWLockExclusive(this + 7);
  v7 = v9;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v7;
}

```

## disassembly

```asm
0x18000f090  mov     [rsp+arg_0], rcx
0x18000f095  push    rbx
0x18000f096  push    rsi
0x18000f097  push    rdi
0x18000f098  push    r14
0x18000f09a  sub     rsp, 68h
0x18000f09e  mov     r14b, r8b
0x18000f0a1  mov     rbx, rcx
0x18000f0a4  mov     r9d, 1; unsigned __int16
0x18000f0aa  mov     r8d, 86h; unsigned __int16
0x18000f0b0  lea     rdx, aCsdrrestoreser; "CSdrRestoreService::StopTracing"
0x18000f0b7  lea     rcx, [rsp+88h+var_68]; this
0x18000f0bc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000f0c1  lea     rdi, [rbx+38h]
0x18000f0c5  mov     rcx, rdi; SRWLock
0x18000f0c8  call    cs:__imp_AcquireSRWLockExclusive
0x18000f0ce  nop
0x18000f0cf  mov     rsi, [rbx+28h]
0x18000f0d3  mov     rcx, rdi; SRWLock
0x18000f0d6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f0dc  mov     eax, 99h
0x18000f0e1  test    rsi, rsi
0x18000f0e4  jnz     short loc_18000F0F5
0x18000f0e6  mov     [rsp+88h+var_68], 80070057h
0x18000f0ee  mov     [rsp+88h+var_62], ax
0x18000f0f3  jmp     short loc_18000F10D
0x18000f0f5  mov     [rsp+88h+var_68], 0
0x18000f0fd  mov     [rsp+88h+var_64], ax
0x18000f102  mov     dl, r14b; unsigned __int8
0x18000f105  mov     rcx, rsi; lpFileName
0x18000f108  call    ?SdStopTracing@@YAJPEBGEE@Z; SdStopTracing(ushort const *,uchar,uchar)
0x18000f10d  mov     rcx, rdi; SRWLock
0x18000f110  call    cs:__imp_AcquireSRWLockExclusive
0x18000f116  nop
0x18000f117  cmp     dword ptr [rbx+30h], 0
0x18000f11b  jz      short loc_18000F12D
0x18000f11d  mov     dword ptr [rbx+30h], 0
0x18000f124  mov     rdx, [rbx+28h]
0x18000f128  xor     eax, eax
0x18000f12a  mov     [rdx], ax
0x18000f12d  mov     rcx, rdi; SRWLock
0x18000f130  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f136  mov     ebx, [rsp+88h+var_68]
0x18000f13a  lea     rcx, [rsp+88h+var_68]; this
0x18000f13f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000f144  mov     eax, ebx
0x18000f146  add     rsp, 68h
0x18000f14a  pop     r14
0x18000f14c  pop     rdi
0x18000f14d  pop     rsi
0x18000f14e  pop     rbx
0x18000f14f  retn
0x180021b95  push    rbp
0x180021b97  sub     rsp, 20h
0x180021b9b  mov     rbp, rdx
0x180021b9e  mov     rcx, [rbp+90h]
0x180021ba5  add     rcx, 38h ; '8'; SRWLock
0x180021ba9  call    cs:__imp_ReleaseSRWLockExclusive
0x180021baf  nop
0x180021bb0  add     rsp, 20h
0x180021bb4  pop     rbp
0x180021bb5  retn
0x180021bb7  push    rbp
0x180021bb9  sub     rsp, 20h
0x180021bbd  mov     rbp, rdx
0x180021bc0  mov     rcx, [rbp+90h]
0x180021bc7  add     rcx, 38h ; '8'; SRWLock
0x180021bcb  call    cs:__imp_ReleaseSRWLockExclusive
0x180021bd1  nop
0x180021bd2  add     rsp, 20h
0x180021bd6  pop     rbp
0x180021bd7  retn
```
