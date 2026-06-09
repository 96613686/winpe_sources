# ValidateTimeoutHeader(IHttpContext *,unsigned __int64 *,char const * *)

- ea: `0x180007540`
- end: `0x180007707`
- name: `?ValidateTimeoutHeader@@YAJPEAVIHttpContext@@PEA_KPEAPEBD@Z`
- size: `455`
- prototype: `__int64 __fastcall(struct IHttpContext *, unsigned __int64 *, const char **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c600`

## callees

- `0x180007540`
- `0x1800224da`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `msvcrt!_strtoui64` at `0x18000760e`
- `msvcrt!_strtoui64` at `0x18000760e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007652`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007652`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007686`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007686`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800076d2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800076d2`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000769d`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000769d`

## pseudocode

```c
__int64 __fastcall ValidateTimeoutHeader(struct IHttpContext *a1, unsigned __int64 *a2, const char **a3)
{
  __int64 v3; // rax
  __int64 v7; // rax
  const char *v8; // rax
  const char *v9; // rbp
  char v10; // al
  unsigned __int64 v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rsi
  __int64 v14; // rbx
  void (__fastcall *v15)(__int64, const wchar_t *, __int64, __int64, char); // rdi
  char *EndPtr; // [rsp+30h] [rbp-78h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v19[32]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v20; // [rsp+60h] [rbp-48h]

  v3 = *(_QWORD *)a1;
  EndPtr = 0;
  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 24))(a1);
  v8 = (const char *)(*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v7 + 24LL))(v7, "Timeout", 0);
  v9 = v8;
  if ( !v8 || !*v8 )
  {
    *a2 = -1;
    *a3 = 0;
    return 0;
  }
  if ( !strncmp_0(v8, "Infinite", 8u) )
  {
    v10 = v9[8];
    if ( !v10 || v10 == 44 )
    {
      *a2 = -1;
LABEL_7:
      *a3 = v9;
      return 0;
    }
  }
  if ( !strncmp_0(v9, "Second-", 7u) )
  {
    EndPtr = 0;
    v11 = _strtoui64(v9 + 7, &EndPtr, 10);
    if ( EndPtr )
    {
      if ( (unsigned __int8)*EndPtr <= 0x2Cu )
      {
        v12 = 0x100100000001LL;
        if ( _bittest64(&v12, *EndPtr) )
        {
          if ( v11 <= 0xFFFFFFFF )
          {
            SystemTimeAsFileTime = 0;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            *a2 = *(_QWORD *)&SystemTimeAsFileTime + 10000000 * v11;
            goto LABEL_7;
          }
        }
      }
    }
  }
  v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  STRU::STRU((STRU *)v19);
  v14 = 0;
  v15 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, __int64, char))(*(_QWORD *)v13 + 32LL);
  if ( (int)STRU::CopyA((STRU *)v19, v9) >= 0 )
    v14 = v20;
  v15(v13, L"Timeout: Header Invalid", v14, 2147942487LL, 3);
  STRU::~STRU((STRU *)v19);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180007540  push    rbx
0x180007542  push    rbp
0x180007543  push    rsi
0x180007544  push    rdi
0x180007545  push    r14
0x180007547  sub     rsp, 80h
0x18000754e  mov     rax, cs:__security_cookie
0x180007555  xor     rax, rsp
0x180007558  mov     [rsp+0A8h+var_30], rax
0x18000755d  mov     rax, [rcx]
0x180007560  mov     rdi, r8
0x180007563  mov     rbx, rdx
0x180007566  mov     [rsp+0A8h+EndPtr], 0
0x18000756f  mov     r14, rcx
0x180007572  mov     rax, [rax+18h]
0x180007576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000757b  mov     r9, rax
0x18000757e  lea     rdx, aTimeout; "Timeout"
0x180007585  xor     r8d, r8d
0x180007588  mov     rcx, [rax]
0x18000758b  mov     rax, [rcx+18h]
0x18000758f  mov     rcx, r9
0x180007592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007597  mov     rbp, rax
0x18000759a  test    rax, rax
0x18000759d  jz      loc_1800076DC
0x1800075a3  cmp     byte ptr [rax], 0
0x1800075a6  jz      loc_1800076DC
0x1800075ac  mov     r8d, 8; MaxCount
0x1800075b2  lea     rdx, aInfinite; "Infinite"
0x1800075b9  mov     rcx, rax; Str1
0x1800075bc  call    strncmp_0
0x1800075c1  test    eax, eax
0x1800075c3  jnz     short loc_1800075DF
0x1800075c5  mov     al, [rbp+8]
0x1800075c8  test    al, al
0x1800075ca  jz      short loc_1800075D0
0x1800075cc  cmp     al, 2Ch ; ','
0x1800075ce  jnz     short loc_1800075DF
0x1800075d0  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800075d7  mov     [rdi], rbp
0x1800075da  jmp     loc_1800076EA
0x1800075df  mov     r8d, 7; MaxCount
0x1800075e5  lea     rdx, aSecond; "Second-"
0x1800075ec  mov     rcx, rbp; Str1
0x1800075ef  call    strncmp_0
0x1800075f4  test    eax, eax
0x1800075f6  jnz     short loc_18000766C
0x1800075f8  lea     rcx, [rbp+7]; String
0x1800075fc  mov     [rsp+0A8h+EndPtr], 0
0x180007605  lea     r8d, [rax+0Ah]; Radix
0x180007609  lea     rdx, [rsp+0A8h+EndPtr]; EndPtr
0x18000760e  call    cs:__imp__strtoui64
0x180007614  mov     rsi, rax
0x180007617  mov     rax, [rsp+0A8h+EndPtr]
0x18000761c  test    rax, rax
0x18000761f  jz      short loc_18000766C
0x180007621  cmp     byte ptr [rax], 2Ch ; ','
0x180007624  ja      short loc_18000766C
0x180007626  movsx   rcx, byte ptr [rax]
0x18000762a  mov     rax, 100100000001h
0x180007634  bt      rax, rcx
0x180007638  jnb     short loc_18000766C
0x18000763a  mov     eax, 0FFFFFFFFh
0x18000763f  cmp     rsi, rax
0x180007642  ja      short loc_18000766C
0x180007644  lea     rcx, [rsp+0A8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007649  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180007652  call    cs:__imp_GetSystemTimeAsFileTime
0x180007658  imul    rax, rsi, 989680h
0x18000765f  add     rax, qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]
0x180007664  mov     [rbx], rax
0x180007667  jmp     loc_1800075D7
0x18000766c  mov     rax, [r14]
0x18000766f  mov     rcx, r14
0x180007672  mov     rax, [rax+110h]
0x180007679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767e  lea     rcx, [rsp+0A8h+var_68]
0x180007683  mov     rsi, rax
0x180007686  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000768c  mov     rcx, [rsi]
0x18000768f  mov     rdx, rbp
0x180007692  xor     ebx, ebx
0x180007694  mov     rdi, [rcx+20h]
0x180007698  lea     rcx, [rsp+0A8h+var_68]
0x18000769d  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x1800076a3  mov     ebp, 80070057h
0x1800076a8  mov     [rsp+0A8h+var_88], 3
0x1800076ad  test    eax, eax
0x1800076af  lea     rdx, aTimeoutHeaderI; "Timeout: Header Invalid"
0x1800076b6  mov     r9d, ebp
0x1800076b9  mov     rcx, rsi
0x1800076bc  cmovns  rbx, [rsp+0A8h+var_48]
0x1800076c2  mov     rax, rdi
0x1800076c5  mov     r8, rbx
0x1800076c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076cd  lea     rcx, [rsp+0A8h+var_68]
0x1800076d2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800076d8  mov     eax, ebp
0x1800076da  jmp     short loc_1800076EC
0x1800076dc  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800076e3  mov     qword ptr [rdi], 0
0x1800076ea  xor     eax, eax
0x1800076ec  mov     rcx, [rsp+0A8h+var_30]
0x1800076f1  xor     rcx, rsp; StackCookie
0x1800076f4  call    __security_check_cookie
0x1800076f9  add     rsp, 80h
0x180007700  pop     r14
0x180007702  pop     rdi
0x180007703  pop     rsi
0x180007704  pop     rbp
0x180007705  pop     rbx
0x180007706  retn
```
