# CWaitShutdown::AreSessionsDrained(int *)

- ea: `0x180013fcc`
- end: `0x180014175`
- name: `?AreSessionsDrained@CWaitShutdown@@AEAAJPEAH@Z`
- size: `425`
- prototype: `__int64 __fastcall(CWaitShutdown *__hidden this, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000129c`
- `0x18002b4d0`

## callees

- `0x180004330`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x1800083fc`
- `0x180008494`
- `0x180008508`
- `0x180013fcc`
- `0x1800249e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001403b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001403b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014087`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014143`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014143`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800140fd`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800140fd`

## string_xrefs

- `0x180014078`: `Failed to open binding`
- `0x1800140b5`: `Enum->Open failed: 0x%x in %s`

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
      EnumResult = CEnum::GetEnumResult((CEnum *)&v16, 1u, (struct _SESSIONENUM **)&hMem, &v19);
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
0x180013fcc  mov     [rsp-28h+arg_0], rbx
0x180013fd1  push    rbp
0x180013fd2  push    rsi
0x180013fd3  push    rdi
0x180013fd4  push    r14
0x180013fd6  push    r15
0x180013fd8  mov     rbp, rsp
0x180013fdb  sub     rsp, 40h
0x180013fdf  mov     r14, rdx
0x180013fe2  mov     [rbp+hMem], 0
0x180013fea  mov     r15, rcx
0x180013fed  mov     [rbp+arg_8], 0
0x180013ff4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013ffb  mov     qword ptr [rbp+var_18], 0
0x180014003  mov     ecx, 40h ; '@'; unsigned __int64
0x180014008  mov     [rbp+arg_10], 0
0x18001400f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014014  test    rax, rax
0x180014017  jz      short loc_18001402A
0x180014019  lea     r9, [rbp+arg_10]; unsigned int *
0x18001401d  xor     r8d, r8d; int
0x180014020  xor     edx, edx; unsigned __int16 *
0x180014022  mov     rcx, rax; this
0x180014025  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x18001402a  mov     [rbp+var_10], rax
0x18001402e  mov     edi, 1
0x180014033  test    rax, rax
0x180014036  jnz     short loc_180014058
0x180014038  lea     ecx, [rax+0Eh]; dwErrCode
0x18001403b  call    cs:__imp_SetLastError
0x180014042  nop     dword ptr [rax+rax+00h]
0x180014047  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18001404e  lea     ecx, [rdi+7]; int
0x180014051  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014056  jmp     short loc_18001405B
0x180014058  mov     dword ptr [rbp+var_18+4], edi
0x18001405b  lea     rcx, [rbp+var_18]; unsigned __int16 *
0x18001405f  mov     [rbp+var_20], 0
0x180014067  mov     dword ptr [r14], 0
0x18001406e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180014073  test    rax, rax
0x180014076  jnz     short loc_18001409A
0x180014078  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18001407f  lea     ecx, [rax+8]; int
0x180014082  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014087  call    cs:__imp_GetLastError
0x18001408e  nop     dword ptr [rax+rax+00h]
0x180014093  mov     ebx, eax
0x180014095  jmp     loc_18001413A
0x18001409a  lea     rcx, [rbp+var_18]; unsigned __int16 *
0x18001409e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800140a3  mov     rdx, rax; void *
0x1800140a6  lea     rcx, [rbp+var_20]; this
0x1800140aa  call    ?Open@CEnum@@QEAAJPEAX@Z; CEnum::Open(void *)
0x1800140af  mov     ebx, eax
0x1800140b1  test    eax, eax
0x1800140b3  jns     short loc_1800140D2
0x1800140b5  lea     rdx, aEnumOpenFailed; "Enum->Open failed: 0x%x in %s"
0x1800140bc  mov     r8d, eax
0x1800140bf  lea     r9, aCwaitshutdownA; "CWaitShutdown::AreSessionsDrained"
0x1800140c6  mov     ecx, 8; int
0x1800140cb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800140d0  jmp     short loc_18001413A
0x1800140d2  lea     r9, [rbp+arg_8]; unsigned int *
0x1800140d6  mov     edx, edi; unsigned int
0x1800140d8  lea     r8, [rbp+hMem]; struct _SESSIONENUM **
0x1800140dc  lea     rcx, [rbp+var_20]; this
0x1800140e0  call    ?GetEnumResult@CEnum@@QEAAJKPEAPEAU_SESSIONENUM@@PEAK@Z; CEnum::GetEnumResult(ulong,_SESSIONENUM * *,ulong *)
0x1800140e5  mov     ebx, eax
0x1800140e7  test    eax, eax
0x1800140e9  jns     short loc_1800140F4
0x1800140eb  lea     rdx, aGetenumresultF; "GetEnumResult failed: 0x%x in %s"
0x1800140f2  jmp     short loc_1800140BC
0x1800140f4  xor     edi, edi
0x1800140f6  xor     esi, esi
0x1800140f8  cmp     [rbp+arg_8], esi
0x1800140fb  jbe     short loc_180014129
0x1800140fd  call    cs:__imp_WTSGetServiceSessionId
0x180014104  nop     dword ptr [rax+rax+00h]
0x180014109  mov     ecx, esi
0x18001410b  imul    rdx, rcx, 68h ; 'h'
0x18001410f  mov     rcx, [rbp+hMem]
0x180014113  cmp     eax, [rdx+rcx+4]
0x180014117  jz      short loc_180014122
0x180014119  cmp     dword ptr [rdx+rcx+8], 8
0x18001411e  jz      short loc_180014122
0x180014120  inc     edi
0x180014122  inc     esi
0x180014124  cmp     esi, [rbp+arg_8]
0x180014127  jb      short loc_1800140FD
0x180014129  xor     eax, eax
0x18001412b  mov     [r15+640h], edi
0x180014132  test    edi, edi
0x180014134  setz    al
0x180014137  mov     [r14], eax
0x18001413a  mov     rcx, [rbp+hMem]; hMem
0x18001413e  test    rcx, rcx
0x180014141  jz      short loc_18001414F
0x180014143  call    cs:__imp_LocalFree
0x18001414a  nop     dword ptr [rax+rax+00h]
0x18001414f  lea     rcx, [rbp+var_20]; this
0x180014153  call    ??1CEnum@@QEAA@XZ; CEnum::~CEnum(void)
0x180014158  lea     rcx, [rbp+var_18]; this
0x18001415c  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180014161  mov     eax, ebx
0x180014163  mov     rbx, [rsp+40h+arg_0]
0x180014168  add     rsp, 40h
0x18001416c  pop     r15
0x18001416e  pop     r14
0x180014170  pop     rdi
0x180014171  pop     rsi
0x180014172  pop     rbp
0x180014173  retn
```
