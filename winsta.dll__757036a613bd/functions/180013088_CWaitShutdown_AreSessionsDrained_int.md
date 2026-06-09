# CWaitShutdown::AreSessionsDrained(int *)

- ea: `0x180013088`
- end: `0x180013218`
- name: `?AreSessionsDrained@CWaitShutdown@@AEAAJPEAH@Z`
- size: `400`
- prototype: `__int64 __fastcall(CWaitShutdown *__hidden this, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000171c`
- `0x180029890`

## callees

- `0x180005db0`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180009ba4`
- `0x180009c10`
- `0x180009c94`
- `0x180013088`
- `0x1800230b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800130f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800130f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001313d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001313d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131ed`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800131ad`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800131ad`

## string_xrefs

- `0x18001312e`: `Failed to open binding`
- `0x180013165`: `Enum->Open failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CWaitShutdown::AreSessionsDrained(CWaitShutdown *this, int *a2)
{
  CPublicBinding *v4; // rax
  DWORD LastError; // ebx
  void *v6; // rax
  int v7; // eax
  int EnumResult; // eax
  __int64 v9; // rdx
  HLOCAL v10; // rcx
  __int64 v11; // r8
  int v12; // edi
  unsigned int i; // esi
  int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 v17[4]; // [rsp+28h] [rbp-18h] BYREF
  CPublicBinding *v18; // [rsp+30h] [rbp-10h]
  unsigned int v19; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v20; // [rsp+80h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+48h] BYREF

  hMem = 0;
  v19 = 0;
  *(_QWORD *)v17 = 0;
  v20 = 0;
  v4 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v4 = CPublicBinding::CPublicBinding(v4, 0, 0, &v20);
  v18 = v4;
  if ( v4 )
  {
    *(_DWORD *)&v17[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  v16 = 0;
  *a2 = 0;
  if ( CSmartPublicBinding::operator void *(v17) )
  {
    v6 = (void *)CSmartPublicBinding::operator void *(v17);
    v7 = CEnum::Open((CEnum *)&v16, v6);
    LastError = v7;
    if ( v7 >= 0 )
    {
      EnumResult = CEnum::GetEnumResult((CEnum *)&v16, 1, (struct _SESSIONENUM **)&hMem, &v19);
      LastError = EnumResult;
      if ( EnumResult >= 0 )
      {
        v12 = 0;
        for ( i = 0; i < v19; ++i )
        {
          v14 = WTSGetServiceSessionId(v10, v9, v11);
          v9 = 104LL * i;
          v10 = hMem;
          if ( v14 != *(_DWORD *)((char *)hMem + v9 + 4) && *(_DWORD *)((char *)hMem + v9 + 8) != 8 )
            ++v12;
        }
        *((_DWORD *)this + 400) = v12;
        *a2 = v12 == 0;
      }
      else
      {
        _DbgPrintMessage(
          8,
          "GetEnumResult failed: 0x%x in %s",
          (unsigned int)EnumResult,
          "CWaitShutdown::AreSessionsDrained");
      }
    }
    else
    {
      _DbgPrintMessage(8, "Enum->Open failed: 0x%x in %s", (unsigned int)v7, "CWaitShutdown::AreSessionsDrained");
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
  }
  if ( hMem )
    LocalFree(hMem);
  CEnum::~CEnum((CEnum *)&v16);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v17);
  return LastError;
}

```

## disassembly

```asm
0x180013088  mov     [rsp-28h+arg_0], rbx
0x18001308d  push    rbp
0x18001308e  push    rsi
0x18001308f  push    rdi
0x180013090  push    r14
0x180013092  push    r15
0x180013094  mov     rbp, rsp
0x180013097  sub     rsp, 40h
0x18001309b  mov     r14, rdx
0x18001309e  mov     [rbp+hMem], 0
0x1800130a6  mov     r15, rcx
0x1800130a9  mov     [rbp+arg_8], 0
0x1800130b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800130b7  mov     qword ptr [rbp+var_18], 0
0x1800130bf  mov     ecx, 40h ; '@'; unsigned __int64
0x1800130c4  mov     [rbp+arg_10], 0
0x1800130cb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800130d0  test    rax, rax
0x1800130d3  jz      short loc_1800130E6
0x1800130d5  lea     r9, [rbp+arg_10]; unsigned int *
0x1800130d9  xor     r8d, r8d; int
0x1800130dc  xor     edx, edx; unsigned __int16 *
0x1800130de  mov     rcx, rax; this
0x1800130e1  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x1800130e6  mov     [rbp+var_10], rax
0x1800130ea  mov     edi, 1
0x1800130ef  test    rax, rax
0x1800130f2  jnz     short loc_18001310E
0x1800130f4  lea     ecx, [rax+0Eh]; dwErrCode
0x1800130f7  call    cs:__imp_SetLastError
0x1800130fd  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180013104  lea     ecx, [rdi+7]; int
0x180013107  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001310c  jmp     short loc_180013111
0x18001310e  mov     dword ptr [rbp+var_18+4], edi
0x180013111  lea     rcx, [rbp+var_18]; unsigned __int16 *
0x180013115  mov     [rbp+var_20], 0
0x18001311d  mov     dword ptr [r14], 0
0x180013124  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180013129  test    rax, rax
0x18001312c  jnz     short loc_18001314A
0x18001312e  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180013135  lea     ecx, [rax+8]; int
0x180013138  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001313d  call    cs:__imp_GetLastError
0x180013143  mov     ebx, eax
0x180013145  jmp     loc_1800131E4
0x18001314a  lea     rcx, [rbp+var_18]; unsigned __int16 *
0x18001314e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180013153  mov     rdx, rax; void *
0x180013156  lea     rcx, [rbp+var_20]; this
0x18001315a  call    ?Open@CEnum@@QEAAJPEAX@Z; CEnum::Open(void *)
0x18001315f  mov     ebx, eax
0x180013161  test    eax, eax
0x180013163  jns     short loc_180013182
0x180013165  lea     rdx, aEnumOpenFailed; "Enum->Open failed: 0x%x in %s"
0x18001316c  mov     r8d, eax
0x18001316f  lea     r9, aCwaitshutdownA; "CWaitShutdown::AreSessionsDrained"
0x180013176  mov     ecx, 8; int
0x18001317b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013180  jmp     short loc_1800131E4
0x180013182  lea     r9, [rbp+arg_8]; unsigned int *
0x180013186  mov     edx, edi; unsigned int
0x180013188  lea     r8, [rbp+hMem]; struct _SESSIONENUM **
0x18001318c  lea     rcx, [rbp+var_20]; this
0x180013190  call    ?GetEnumResult@CEnum@@QEAAJKPEAPEAU_SESSIONENUM@@PEAK@Z; CEnum::GetEnumResult(ulong,_SESSIONENUM * *,ulong *)
0x180013195  mov     ebx, eax
0x180013197  test    eax, eax
0x180013199  jns     short loc_1800131A4
0x18001319b  lea     rdx, aGetenumresultF; "GetEnumResult failed: 0x%x in %s"
0x1800131a2  jmp     short loc_18001316C
0x1800131a4  xor     edi, edi
0x1800131a6  xor     esi, esi
0x1800131a8  cmp     [rbp+arg_8], esi
0x1800131ab  jbe     short loc_1800131D3
0x1800131ad  call    cs:__imp_WTSGetServiceSessionId
0x1800131b3  mov     ecx, esi
0x1800131b5  imul    rdx, rcx, 68h ; 'h'
0x1800131b9  mov     rcx, [rbp+hMem]
0x1800131bd  cmp     eax, [rdx+rcx+4]
0x1800131c1  jz      short loc_1800131CC
0x1800131c3  cmp     dword ptr [rdx+rcx+8], 8
0x1800131c8  jz      short loc_1800131CC
0x1800131ca  inc     edi
0x1800131cc  inc     esi
0x1800131ce  cmp     esi, [rbp+arg_8]
0x1800131d1  jb      short loc_1800131AD
0x1800131d3  xor     eax, eax
0x1800131d5  mov     [r15+640h], edi
0x1800131dc  test    edi, edi
0x1800131de  setz    al
0x1800131e1  mov     [r14], eax
0x1800131e4  mov     rcx, [rbp+hMem]; hMem
0x1800131e8  test    rcx, rcx
0x1800131eb  jz      short loc_1800131F3
0x1800131ed  call    cs:__imp_LocalFree
0x1800131f3  lea     rcx, [rbp+var_20]; this
0x1800131f7  call    ??1CEnum@@QEAA@XZ; CEnum::~CEnum(void)
0x1800131fc  lea     rcx, [rbp+var_18]; this
0x180013200  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180013205  mov     eax, ebx
0x180013207  mov     rbx, [rsp+40h+arg_0]
0x18001320c  add     rsp, 40h
0x180013210  pop     r15
0x180013212  pop     r14
0x180013214  pop     rdi
0x180013215  pop     rsi
0x180013216  pop     rbp
0x180013217  retn
```
