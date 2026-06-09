# CSdrRestoreService::StartTracing(ushort * *)

- ea: `0x18000efb0`
- end: `0x18000f081`
- name: `?StartTracing@CSdrRestoreService@@UEAAJPEAPEAG@Z`
- size: `209`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, LPVOID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18000efb0`
- `0x18001586c`
- `0x180015974`
- `0x180016520`
- `0x18001f624`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f02b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f02b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021b81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021b81`

## string_xrefs

- `0x18000efd4`: `CSdrRestoreService::StartTracing`

## pseudocode

```c
__int64 __fastcall CSdrRestoreService::StartTracing(RTL_SRWLOCK *this, LPVOID *a2)
{
  __int16 v4; // ax
  int started; // ebx
  CBsString *v6; // rcx
  unsigned __int16 *v7; // rdx
  int v9; // [rsp+20h] [rbp-48h] BYREF
  __int16 v10; // [rsp+24h] [rbp-44h]
  __int16 v11; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CSdrRestoreService::StartTracing", 101, 1);
  v4 = 102;
  if ( !a2 )
  {
    started = -2147024809;
    v9 = -2147024809;
LABEL_3:
    v11 = v4;
    goto LABEL_8;
  }
  v9 = 0;
  v10 = 102;
  started = SdStartTracing(a2);
  v9 = started;
  v4 = 104;
  if ( started < 0 )
    goto LABEL_3;
  v10 = 104;
  AcquireSRWLockExclusive(this + 7);
  v6 = (CBsString *)&this[5];
  v7 = (unsigned __int16 *)*a2;
  if ( LODWORD(this[6].Ptr) )
  {
    LODWORD(this[6].Ptr) = 0;
    **(_WORD **)v6 = 0;
  }
  CBsString::Append(v6, v7);
  ReleaseSRWLockExclusive(this + 7);
  started = v9;
LABEL_8:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000efb0  mov     rax, rsp
0x18000efb3  mov     [rax+10h], rbx
0x18000efb7  mov     [rax+18h], rsi
0x18000efbb  mov     [rax+8], rcx
0x18000efbf  push    rdi
0x18000efc0  sub     rsp, 60h
0x18000efc4  mov     rsi, rdx
0x18000efc7  mov     rdi, rcx
0x18000efca  mov     r9d, 1; unsigned __int16
0x18000efd0  lea     r8d, [r9+64h]; unsigned __int16
0x18000efd4  lea     rdx, aCsdrrestoreser_2; "CSdrRestoreService::StartTracing"
0x18000efdb  lea     rcx, [rax-48h]; this
0x18000efdf  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000efe4  mov     eax, 66h ; 'f'
0x18000efe9  test    rsi, rsi
0x18000efec  jnz     short loc_18000EFFE
0x18000efee  mov     ebx, 80070057h
0x18000eff3  mov     [rsp+68h+var_48], ebx
0x18000eff7  mov     [rsp+68h+var_42], ax
0x18000effc  jmp     short loc_18000F063
0x18000effe  mov     [rsp+68h+var_48], 0
0x18000f006  mov     [rsp+68h+var_44], ax
0x18000f00b  mov     rcx, rsi; unsigned __int16 **
0x18000f00e  call    ?SdStartTracing@@YAJPEAPEAG@Z; SdStartTracing(ushort * *)
0x18000f013  mov     ebx, eax
0x18000f015  mov     [rsp+68h+var_48], eax
0x18000f019  test    eax, eax
0x18000f01b  mov     eax, 68h ; 'h'
0x18000f020  js      short loc_18000EFF7
0x18000f022  mov     [rsp+68h+var_44], ax
0x18000f027  lea     rcx, [rdi+38h]; SRWLock
0x18000f02b  call    cs:__imp_AcquireSRWLockExclusive
0x18000f031  nop
0x18000f032  lea     rcx, [rdi+28h]; this
0x18000f036  mov     rdx, [rsi]; unsigned __int16 *
0x18000f039  cmp     dword ptr [rcx+8], 0
0x18000f03d  jz      short loc_18000F04F
0x18000f03f  mov     dword ptr [rcx+8], 0
0x18000f046  mov     r8, [rcx]
0x18000f049  xor     eax, eax
0x18000f04b  mov     [r8], ax
0x18000f04f  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000f054  nop
0x18000f055  lea     rcx, [rdi+38h]; SRWLock
0x18000f059  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f05f  mov     ebx, [rsp+68h+var_48]
0x18000f063  lea     rcx, [rsp+68h+var_48]; this
0x18000f068  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000f06d  mov     eax, ebx
0x18000f06f  lea     r11, [rsp+68h+var_8]
0x18000f074  mov     rbx, [r11+18h]
0x18000f078  mov     rsi, [r11+20h]
0x18000f07c  mov     rsp, r11
0x18000f07f  pop     rdi
0x18000f080  retn
0x180021b70  push    rbp
0x180021b72  sub     rsp, 20h
0x180021b76  mov     rbp, rdx
0x180021b79  mov     rcx, [rbp+70h]
0x180021b7d  add     rcx, 38h ; '8'; SRWLock
0x180021b81  call    cs:__imp_ReleaseSRWLockExclusive
0x180021b87  nop
0x180021b88  add     rsp, 20h
0x180021b8c  pop     rbp
0x180021b8d  retn
```
