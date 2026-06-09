# CAccountFilter::_IterateAccounts(ushort const *,ulong)

- ea: `0x180007690`
- end: `0x1800078a2`
- name: `?_IterateAccounts@CAccountFilter@@AEAAJPEBGK@Z`
- size: `530`
- prototype: `int(CAccountFilter *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016834`

## callees

- `0x180007690`
- `0x1800078b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800076b9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800076b9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000779e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800077c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000780a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000779e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800077c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000780a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000785d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000785d`

## pseudocode

```c
__int64 __fastcall CAccountFilter::_IterateAccounts(CAccountFilter *this, const unsigned __int16 *a2, unsigned int a3)
{
  __int64 result; // rax
  BOOL v6; // ecx
  unsigned int v7; // edi
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  const WCHAR *v11; // r8
  int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  CAccountFilter *v16; // rcx
  CAccountFilter *pvData; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF

  pvData = this;
  InitOnceExecuteOnce(&g_accountFilter, CAccountFilter::s_InitializeOnce, &g_accountFilter, 0);
  result = (unsigned int)dword_180020388;
  if ( dword_180020388 >= 0 )
  {
    v6 = 0;
    v7 = 0;
    if ( !dword_180020398 )
      goto LABEL_6;
    do
    {
      if ( v6 )
        return 0;
      v8 = CAccountFilter::_Compare(
             (CAccountFilter *)(520LL * v7),
             a2,
             (const unsigned __int16 *)Block + 260 * v7 + 2,
             *((_DWORD *)Block + 130 * v7),
             a3);
      ++v7;
      v6 = v8;
    }
    while ( v7 < dword_180020398 );
    if ( !v8 )
    {
LABEL_6:
      v9 = 0;
      while ( 1 )
      {
        if ( v6 )
          return 0;
        v10 = 65LL * v9;
        v11 = (const WCHAR *)&qword_1800193A0[v10] + 2;
        v12 = qword_1800193A0[v10];
        if ( (v12 & 0xFFFF0000) != 0 )
        {
          if ( (qword_1800193A0[v10] & 0xFFFF0000) != 0x10000 )
            goto LABEL_19;
          v13 = -1;
          do
            ++v13;
          while ( v11[v13] );
          v14 = -1;
          do
            ++v14;
          while ( a2[v14] );
          if ( (int)v14 < (int)v13 )
          {
LABEL_19:
            v6 = 0;
            goto LABEL_20;
          }
          v15 = CompareStringOrdinal(a2, v13, v11, v13, 1);
          v6 = v15 == 2;
          if ( v15 != 2 )
            goto LABEL_20;
        }
        else if ( CompareStringOrdinal(a2, -1, v11, -1, 1) != 2 )
        {
          goto LABEL_19;
        }
        v6 = (unsigned __int16)v12 == a3;
LABEL_20:
        if ( ++v9 >= 8 )
        {
          if ( !v6 )
          {
            if ( CompareStringOrdinal(a2, -1, L"DefaultAccount", -1, 1) != 2 )
              return 1;
            LODWORD(pvData) = 0;
            pcbData = 4;
            if ( RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\SpecialAccounts\\UserList",
                   L"DefaultAccount",
                   0x10u,
                   0,
                   &pvData,
                   &pcbData)
              || !CAccountFilter::_Compare(v16, a2, L"DefaultAccount", (unsigned int)pvData, a3) )
            {
              return 1;
            }
          }
          return 0;
        }
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007690  mov     [rsp+arg_0], rcx
0x180007695  push    rbx
0x180007696  push    rbp
0x180007697  sub     rsp, 48h
0x18000769b  mov     ebp, r8d
0x18000769e  lea     rcx, ?g_accountFilter@@3VCAccountFilter@@A; InitOnce
0x1800076a5  mov     rbx, rdx
0x1800076a8  lea     r8, ?g_accountFilter@@3VCAccountFilter@@A; Parameter
0x1800076af  lea     rdx, ?s_InitializeOnce@CAccountFilter@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800076b6  xor     r9d, r9d; Context
0x1800076b9  call    cs:__imp_InitOnceExecuteOnce
0x1800076bf  mov     eax, cs:dword_180020388
0x1800076c5  test    eax, eax
0x1800076c7  js      loc_18000789B
0x1800076cd  mov     [rsp+58h+arg_10], rdi
0x1800076d2  xor     ecx, ecx
0x1800076d4  xor     edi, edi
0x1800076d6  mov     [rsp+58h+arg_8], rsi
0x1800076db  cmp     cs:dword_180020398, ecx
0x1800076e1  mov     [rsp+58h+var_18], r14
0x1800076e6  jbe     short loc_18000772B
0x1800076e8  test    ecx, ecx
0x1800076ea  jnz     loc_18000788A
0x1800076f0  mov     eax, edi
0x1800076f2  mov     rdx, rbx; unsigned __int16 *
0x1800076f5  imul    rcx, rax, 208h; this
0x1800076fc  mov     rax, cs:Block
0x180007703  mov     [rsp+58h+bIgnoreCase], ebp; unsigned int
0x180007707  mov     r9d, [rcx+rax]; unsigned int
0x18000770b  lea     r8, [rax+4]
0x18000770f  add     r8, rcx; unsigned __int16 *
0x180007712  call    ?_Compare@CAccountFilter@@AEAAHPEBG0KK@Z; CAccountFilter::_Compare(ushort const *,ushort const *,ulong,ulong)
0x180007717  inc     edi
0x180007719  mov     ecx, eax
0x18000771b  cmp     edi, cs:dword_180020398
0x180007721  jb      short loc_1800076E8
0x180007723  test    eax, eax
0x180007725  jnz     loc_18000788A
0x18000772b  xor     edi, edi
0x18000772d  lea     r14, qword_1800193A0
0x180007734  test    ecx, ecx
0x180007736  jnz     loc_18000788A
0x18000773c  mov     eax, edi
0x18000773e  lea     r8, [r14+4]
0x180007742  imul    rcx, rax, 208h
0x180007749  add     r8, rcx; lpString2
0x18000774c  mov     esi, [rcx+r14]
0x180007750  mov     eax, esi
0x180007752  and     eax, 0FFFF0000h
0x180007757  jz      short loc_1800077B0
0x180007759  cmp     eax, 10000h
0x18000775e  jnz     short loc_1800077DA
0x180007760  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180007767  nop     word ptr [rax+rax+00000000h]
0x180007770  inc     rdx; cchCount1
0x180007773  cmp     word ptr [r8+rdx*2], 0
0x180007779  jnz     short loc_180007770
0x18000777b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007782  inc     rax
0x180007785  cmp     word ptr [rbx+rax*2], 0
0x18000778a  jnz     short loc_180007782
0x18000778c  cmp     eax, edx
0x18000778e  jl      short loc_1800077DA
0x180007790  mov     r9d, edx; cchCount2
0x180007793  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18000779b  mov     rcx, rbx; lpString1
0x18000779e  call    cs:__imp_CompareStringOrdinal
0x1800077a4  xor     ecx, ecx
0x1800077a6  cmp     eax, 2
0x1800077a9  setz    cl
0x1800077ac  jz      short loc_1800077CE
0x1800077ae  jmp     short loc_1800077DC
0x1800077b0  mov     edx, 0FFFFFFFFh; cchCount1
0x1800077b5  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800077bd  mov     r9d, edx; cchCount2
0x1800077c0  mov     rcx, rbx; lpString1
0x1800077c3  call    cs:__imp_CompareStringOrdinal
0x1800077c9  cmp     eax, 2
0x1800077cc  jnz     short loc_1800077DA
0x1800077ce  xor     ecx, ecx
0x1800077d0  movzx   eax, si
0x1800077d3  cmp     eax, ebp
0x1800077d5  setz    cl
0x1800077d8  jmp     short loc_1800077DC
0x1800077da  xor     ecx, ecx
0x1800077dc  inc     edi
0x1800077de  cmp     edi, 8
0x1800077e1  jb      loc_180007734
0x1800077e7  test    ecx, ecx
0x1800077e9  jnz     loc_18000788A
0x1800077ef  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800077f5  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800077fd  mov     edx, r9d; cchCount1
0x180007800  lea     r8, Value; "DefaultAccount"
0x180007807  mov     rcx, rbx; lpString1
0x18000780a  call    cs:__imp_CompareStringOrdinal
0x180007810  cmp     eax, 2
0x180007813  jnz     short loc_180007883
0x180007815  lea     rax, [rsp+58h+arg_18]
0x18000781a  mov     dword ptr [rsp+58h+arg_0], 0
0x180007822  mov     [rsp+58h+pcbData], rax; pcbData
0x180007827  lea     r8, Value; "DefaultAccount"
0x18000782e  lea     rax, [rsp+58h+arg_0]
0x180007833  mov     [rsp+58h+arg_18], 4
0x18000783b  mov     [rsp+58h+pvData], rax; pvData
0x180007840  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180007847  mov     r9d, 10h; dwFlags
0x18000784d  mov     qword ptr [rsp+58h+bIgnoreCase], 0; pdwType
0x180007856  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000785d  call    cs:__imp_RegGetValueW
0x180007863  test    eax, eax
0x180007865  jnz     short loc_180007883
0x180007867  mov     r9d, dword ptr [rsp+58h+arg_0]; unsigned int
0x18000786c  lea     r8, Value; "DefaultAccount"
0x180007873  mov     rdx, rbx; unsigned __int16 *
0x180007876  mov     [rsp+58h+bIgnoreCase], ebp; unsigned int
0x18000787a  call    ?_Compare@CAccountFilter@@AEAAHPEBG0KK@Z; CAccountFilter::_Compare(ushort const *,ushort const *,ulong,ulong)
0x18000787f  test    eax, eax
0x180007881  jnz     short loc_18000788A
0x180007883  mov     eax, 1
0x180007888  jmp     short loc_18000788C
0x18000788a  xor     eax, eax
0x18000788c  mov     rsi, [rsp+58h+arg_8]
0x180007891  mov     r14, [rsp+58h+var_18]
0x180007896  mov     rdi, [rsp+58h+arg_10]
0x18000789b  add     rsp, 48h
0x18000789f  pop     rbp
0x1800078a0  pop     rbx
0x1800078a1  retn
```
