# RtlCreateFunctionOverrideFixupInfo

- ea: `0x1400dbb60`
- end: `0x1400dbcf5`
- name: `RtlCreateFunctionOverrideFixupInfo`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400dba50`

## callees

- `0x14000f0f0`
- `0x140037e68`
- `0x1400da5b4`
- `0x1400daa0c`
- `0x1400db778`
- `0x1400dbb60`
- `0x1400f9780`

## pseudocode

```c
__int64 __fastcall RtlCreateFunctionOverrideFixupInfo(
        gsl::details *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        struct _RTL_FUNCTION_OVERRIDE_INFORMATION **a7)
{
  gsl::details *v8; // r11
  char *v9; // rdi
  int FunctionOverrideDvrtRecord; // eax
  unsigned int FunctionOverrideFixupInfo; // ebx
  unsigned __int64 v12; // rbx
  char *Pool; // rax
  void *v14; // rdx
  size_t Size; // [rsp+30h] [rbp-58h] BYREF
  void *Src; // [rsp+38h] [rbp-50h]
  __int64 v18; // [rsp+40h] [rbp-48h] BYREF
  char *v19; // [rsp+48h] [rbp-40h]
  unsigned __int64 v20; // [rsp+50h] [rbp-38h]
  char *v21; // [rsp+58h] [rbp-30h]

  v8 = a1;
  Size = 0;
  Src = 0;
  if ( !a1 && a2 )
    goto LABEL_19;
  *a7 = 0;
  a1 = (gsl::details *)a3;
  if ( a2 < (unsigned __int64)a3 || a2 - (unsigned __int64)a3 < (unsigned __int64)*(unsigned int *)(a4 + 4) + 8 )
    goto LABEL_19;
  v9 = 0;
  v18 = *(unsigned int *)(a4 + 4) + 8LL;
  v19 = (char *)v8 + a3;
  FunctionOverrideDvrtRecord = RtlpFindFunctionOverrideDvrtRecord(&v18, &Size);
  FunctionOverrideFixupInfo = FunctionOverrideDvrtRecord;
  if ( FunctionOverrideDvrtRecord == -1073741275 || FunctionOverrideDvrtRecord == -1073741637 )
  {
    FunctionOverrideFixupInfo = 0;
    goto LABEL_16;
  }
  if ( FunctionOverrideDvrtRecord < 0 )
    goto LABEL_16;
  v12 = Size;
  Pool = (char *)SkAllocatePool(512, Size);
  v9 = Pool;
  if ( !Pool )
  {
    FunctionOverrideFixupInfo = -1073741801;
    goto LABEL_16;
  }
  if ( v12 == -1 )
LABEL_19:
    `gsl::details::get_terminate_handler'::`2'::handler(a1);
  v14 = Src;
  v18 = v12;
  v19 = (char *)Src;
  if ( !Src && v12 )
    `gsl::details::get_terminate_handler'::`2'::handler(a1);
  Size = v12;
  Src = Pool;
  v20 = v12;
  v21 = Pool;
  memmove(Pool, v14, v12);
  v18 = v12;
  v19 = v9;
  FunctionOverrideFixupInfo = RtlpCreateFunctionOverrideFixupInfo((unsigned __int64 *)&v18, a2, a5, a6, a7, 0);
LABEL_16:
  if ( v9 )
    SkFreePool(512, v9);
  return FunctionOverrideFixupInfo;
}

```

## disassembly

```asm
0x1400dbb60  push    rbx
0x1400dbb62  push    rsi
0x1400dbb63  push    rdi
0x1400dbb64  push    r14
0x1400dbb66  sub     rsp, 68h
0x1400dbb6a  mov     r14d, edx
0x1400dbb6d  mov     r11, rcx
0x1400dbb70  mov     [rsp+88h+Size], 0
0x1400dbb79  mov     [rsp+88h+Src], 0
0x1400dbb82  mov     r10d, edx
0x1400dbb85  test    rcx, rcx
0x1400dbb88  jnz     short loc_1400DBB92
0x1400dbb8a  test    edx, edx
0x1400dbb8c  jnz     loc_1400DBCE8
0x1400dbb92  mov     rsi, [rsp+88h+arg_30]
0x1400dbb9a  mov     qword ptr [rsi], 0
0x1400dbba1  mov     ecx, r8d
0x1400dbba4  cmp     r10, rcx
0x1400dbba7  jb      loc_1400DBCE8
0x1400dbbad  mov     eax, [r9+4]
0x1400dbbb1  add     rax, 8
0x1400dbbb5  sub     r10, rcx
0x1400dbbb8  cmp     r10, rax
0x1400dbbbb  jb      loc_1400DBCE8
0x1400dbbc1  xor     edi, edi
0x1400dbbc3  mov     [rsp+88h+var_48], rax
0x1400dbbc8  lea     rax, [rcx+r11]
0x1400dbbcc  mov     [rsp+88h+var_40], rax
0x1400dbbd1  lea     rdx, [rsp+88h+Size]
0x1400dbbd6  lea     rcx, [rsp+88h+var_48]
0x1400dbbdb  call    ?RtlpFindFunctionOverrideDvrtRecord@@YAJV?$span@$$CBE$0?0@gsl@@PEAV12@@Z; RtlpFindFunctionOverrideDvrtRecord(gsl::span<uchar const,-1>,gsl::span<uchar const,-1> *)
0x1400dbbe0  mov     ebx, eax
0x1400dbbe2  cmp     eax, 0C0000225h
0x1400dbbe7  jz      loc_1400DBCC7
0x1400dbbed  cmp     eax, 0C00000BBh
0x1400dbbf2  jz      loc_1400DBCC7
0x1400dbbf8  test    eax, eax
0x1400dbbfa  js      loc_1400DBCC9
0x1400dbc00  mov     r8d, 6F467452h
0x1400dbc06  mov     rbx, [rsp+88h+Size]
0x1400dbc0b  mov     rdx, rbx
0x1400dbc0e  mov     ecx, 200h
0x1400dbc13  call    SkAllocatePool
0x1400dbc18  mov     rdi, rax
0x1400dbc1b  mov     [rsp+88h+arg_38], rax
0x1400dbc23  test    rax, rax
0x1400dbc26  jnz     short loc_1400DBC32
0x1400dbc28  mov     ebx, 0C0000017h
0x1400dbc2d  jmp     loc_1400DBCC9
0x1400dbc32  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400dbc36  jz      loc_1400DBCE8
0x1400dbc3c  mov     rdx, [rsp+88h+Src]; Src
0x1400dbc41  mov     [rsp+88h+var_48], rbx
0x1400dbc46  mov     [rsp+88h+var_40], rdx
0x1400dbc4b  test    rdx, rdx
0x1400dbc4e  jnz     short loc_1400DBC62
0x1400dbc50  test    rbx, rbx
0x1400dbc53  jz      short loc_1400DBC62
0x1400dbc55  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x1400dbc5c  call    rax ; gsl::details::default_terminate_handler(void); gsl::details::default_terminate_handler(void)
0x1400dbc62  mov     [rsp+88h+Size], rbx
0x1400dbc67  mov     [rsp+88h+Src], rdi
0x1400dbc6c  mov     [rsp+88h+var_38], rbx
0x1400dbc71  mov     [rsp+88h+var_30], rdi
0x1400dbc76  mov     r8, rbx; Size
0x1400dbc79  mov     rcx, rdi; void *
0x1400dbc7c  call    memmove
0x1400dbc81  nop
0x1400dbc82  mov     [rsp+88h+var_48], rbx
0x1400dbc87  mov     [rsp+88h+var_40], rdi
0x1400dbc8c  mov     [rsp+88h+var_60], 0
0x1400dbc95  mov     [rsp+88h+var_68], rsi
0x1400dbc9a  mov     r9, [rsp+88h+arg_28]
0x1400dbca2  mov     r8d, [rsp+88h+arg_20]
0x1400dbcaa  mov     edx, r14d
0x1400dbcad  lea     rcx, [rsp+88h+var_48]
0x1400dbcb2  call    ?RtlpCreateFunctionOverrideFixupInfo@@YAJV?$span@$$CBE$0?0@gsl@@KKPEBU_RTL_FUNCTION_OVERRIDE_CAPABILITIES@@PEAPEAU_RTL_FUNCTION_OVERRIDE_INFORMATION@@PEBU_RTL_SYSTEM_OVERRIDE_INFORMATION@@@Z; RtlpCreateFunctionOverrideFixupInfo(gsl::span<uchar const,-1>,ulong,ulong,_RTL_FUNCTION_OVERRIDE_CAPABILITIES const *,_RTL_FUNCTION_OVERRIDE_INFORMATION * *,_RTL_SYSTEM_OVERRIDE_INFORMATION const *)
0x1400dbcb7  mov     ebx, eax
0x1400dbcb9  jmp     short loc_1400DBCC9
0x1400dbcbb  mov     ebx, eax
0x1400dbcbd  mov     rdi, [rsp+88h+arg_38]
0x1400dbcc5  jmp     short loc_1400DBCC9
0x1400dbcc7  xor     ebx, ebx
0x1400dbcc9  test    rdi, rdi
0x1400dbccc  jz      short loc_1400DBCDB
0x1400dbcce  mov     rdx, rdi
0x1400dbcd1  mov     ecx, 200h
0x1400dbcd6  call    SkFreePool
0x1400dbcdb  mov     eax, ebx
0x1400dbcdd  add     rsp, 68h
0x1400dbce1  pop     r14
0x1400dbce3  pop     rdi
0x1400dbce4  pop     rsi
0x1400dbce5  pop     rbx
0x1400dbce6  retn
0x1400dbce8  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x1400dbcef  call    rax ; gsl::details::default_terminate_handler(void); gsl::details::default_terminate_handler(void)
```
