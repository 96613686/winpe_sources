# parse_key

- ea: `0x1800032e0`
- end: `0x18000348f`
- name: `parse_key`
- size: `431`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *Str1@<rcx>, REGSAM samDesired@<edx>, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003af0`
- `0x18000cc80`

## callees

- `0x1800032e0`
- `0x180010206`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `msvcrt!_mbsnbcmp` at `0x180003342`
- `msvcrt!_mbsnbcmp` at `0x180003342`
- `msvcrt!_mbsrchr` at `0x180003368`
- `msvcrt!_mbsrchr` at `0x180003368`
- `ADVAPI32!RegOpenKeyExA` at `0x1800033fd`
- `ADVAPI32!RegOpenKeyExA` at `0x1800033fd`
- `ADVAPI32!RegCreateKeyExA` at `0x180003484`
- `ADVAPI32!RegCreateKeyExA` at `0x180003484`

## pseudocode

```c
LSTATUS __fastcall parse_key(unsigned __int8 *Str1, REGSAM samDesired, HKEY *a3, const unsigned __int8 **a4, int a5)
{
  char **i; // rbx
  const unsigned __int8 *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdi
  HKEY v13; // rbx
  const unsigned __int8 *v14; // rsi
  unsigned __int8 *v15; // rax
  unsigned __int8 *v16; // r14
  size_t v17; // r15
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  const unsigned __int8 **v22; // rcx
  LSTATUS result; // eax
  __int64 v24; // [rsp+0h] [rbp-50h] BYREF
  CHAR SubKey[8]; // [rsp+50h] [rbp+0h] BYREF
  const unsigned __int8 **v26; // [rsp+58h] [rbp+8h]

  v26 = a4;
  for ( i = &off_1800184C0; ; i += 2 )
  {
    v10 = (const unsigned __int8 *)*i;
    if ( !*i )
      return -2147024893;
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v12 = (int)v11;
    if ( !_mbsnbcmp(Str1, v10, (int)v11) )
      break;
  }
  v13 = (HKEY)i[1];
  if ( !v13 )
    return -2147024893;
  v14 = &Str1[v12];
  v15 = _mbsrchr(v14, 0x5Cu);
  v16 = v15;
  if ( v15 )
  {
    v17 = (int)v15 - (int)v14;
    v18 = v17 + 16;
    if ( v17 + 16 <= v17 + 1 )
      v18 = 0xFFFFFFFFFFFFFF0LL;
    v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
    v20 = alloca(v19);
    v21 = alloca(v19);
    if ( &v24 == (__int64 *)-80LL )
    {
      return -2147024882;
    }
    else
    {
      memcpy_0(SubKey, v14, v17);
      v22 = v26;
      SubKey[v17] = 0;
      *v22 = v16 + 1;
      *(_QWORD *)SubKey = 0;
      if ( a5 && (samDesired & 0x20006) != 0 )
        result = RegCreateKeyExA(v13, SubKey, 0, 0, 0, samDesired, 0, (PHKEY)SubKey, 0);
      else
        result = RegOpenKeyExA(v13, SubKey, 0, samDesired, (PHKEY)SubKey);
      if ( result )
      {
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
      else
      {
        *a3 = *(HKEY *)SubKey;
        return 0;
      }
    }
  }
  else
  {
    *a3 = v13;
    result = 0;
    *a4 = v14;
  }
  return result;
}

```

## disassembly

```asm
0x1800032e0  push    rbp
0x1800032e2  push    rbx
0x1800032e3  push    rsi
0x1800032e4  push    rdi
0x1800032e5  push    r12
0x1800032e7  push    r13
0x1800032e9  push    r14
0x1800032eb  push    r15
0x1800032ed  sub     rsp, 78h
0x1800032f1  lea     rbp, [rsp+50h]
0x1800032f6  mov     rax, cs:__security_cookie
0x1800032fd  xor     rax, rbp
0x180003300  mov     [rbp+60h+var_50], rax
0x180003304  mov     r15, r9
0x180003307  mov     [rbp+60h+var_58], r9
0x18000330b  mov     r13, r8
0x18000330e  lea     rbx, off_1800184C0; "HKCU\\"
0x180003315  mov     r12d, edx
0x180003318  mov     rsi, rcx
0x18000331b  mov     rdx, [rbx]; Str2
0x18000331e  test    rdx, rdx
0x180003321  jz      loc_180003413
0x180003327  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000332e  xchg    ax, ax
0x180003330  inc     rax
0x180003333  cmp     byte ptr [rdx+rax], 0
0x180003337  jnz     short loc_180003330
0x180003339  movsxd  rdi, eax
0x18000333c  mov     rcx, rsi; Str1
0x18000333f  mov     r8, rdi; MaxCount
0x180003342  call    cs:__imp__mbsnbcmp
0x180003348  test    eax, eax
0x18000334a  jnz     loc_18000344C
0x180003350  mov     rbx, [rbx+8]
0x180003354  test    rbx, rbx
0x180003357  jz      loc_180003413
0x18000335d  add     rsi, rdi
0x180003360  mov     edx, 5Ch ; '\'; C
0x180003365  mov     rcx, rsi; String
0x180003368  call    cs:__imp__mbsrchr
0x18000336e  mov     r14, rax
0x180003371  test    rax, rax
0x180003374  jz      loc_180003441
0x18000337a  sub     eax, esi
0x18000337c  movsxd  r15, eax
0x18000337f  lea     rax, [r15+1]
0x180003383  lea     rcx, [rax+0Fh]
0x180003387  cmp     rcx, rax
0x18000338a  ja      short loc_180003396
0x18000338c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180003396  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000339a  mov     rax, rcx
0x18000339d  call    _alloca_probe
0x1800033a2  sub     rsp, rcx
0x1800033a5  lea     rdi, [rsp+0B0h+SubKey]
0x1800033aa  test    rdi, rdi
0x1800033ad  jz      loc_180003455
0x1800033b3  mov     r8, r15; Size
0x1800033b6  mov     rdx, rsi; Src
0x1800033b9  mov     rcx, rdi; void *
0x1800033bc  call    memcpy_0
0x1800033c1  mov     rcx, [rbp+60h+var_58]
0x1800033c5  lea     rax, [r14+1]
0x1800033c9  mov     byte ptr [r15+rdi], 0
0x1800033ce  mov     [rcx], rax
0x1800033d1  xor     ecx, ecx
0x1800033d3  mov     qword ptr [rbp+60h+SubKey], rcx
0x1800033d7  cmp     [rbp+60h+arg_20], ecx
0x1800033dd  jz      short loc_1800033E8
0x1800033df  test    r12d, 20006h
0x1800033e6  jnz     short loc_18000345C
0x1800033e8  lea     rax, [rbp+60h+SubKey]
0x1800033ec  mov     r9d, r12d; samDesired
0x1800033ef  xor     r8d, r8d; ulOptions
0x1800033f2  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800033f7  mov     rdx, rdi; lpSubKey
0x1800033fa  mov     rcx, rbx; hKey
0x1800033fd  call    cs:__imp_RegOpenKeyExA
0x180003403  test    eax, eax
0x180003405  jnz     short loc_180003435
0x180003407  mov     rax, qword ptr [rbp+60h+SubKey]
0x18000340b  mov     [r13+0], rax
0x18000340f  xor     eax, eax
0x180003411  jmp     short loc_180003418
0x180003413  mov     eax, 80070003h
0x180003418  mov     rcx, [rbp+60h+var_50]
0x18000341c  xor     rcx, rbp; StackCookie
0x18000341f  call    __security_check_cookie
0x180003424  lea     rsp, [rbp+28h]
0x180003428  pop     r15
0x18000342a  pop     r14
0x18000342c  pop     r13
0x18000342e  pop     r12
0x180003430  pop     rdi
0x180003431  pop     rsi
0x180003432  pop     rbx
0x180003433  pop     rbp
0x180003434  retn
0x180003435  jle     short loc_180003418
0x180003437  movzx   eax, ax
0x18000343a  or      eax, 80070000h
0x18000343f  jmp     short loc_180003418
0x180003441  mov     [r13+0], rbx
0x180003445  xor     eax, eax
0x180003447  mov     [r15], rsi
0x18000344a  jmp     short loc_180003418
0x18000344c  add     rbx, 10h
0x180003450  jmp     loc_18000331B
0x180003455  mov     eax, 8007000Eh
0x18000345a  jmp     short loc_180003418
0x18000345c  mov     [rsp+0B0h+lpdwDisposition], rcx; lpdwDisposition
0x180003461  lea     rax, [rbp+60h+SubKey]
0x180003465  mov     [rsp+0B0h+var_78], rax; phkResult
0x18000346a  xor     r9d, r9d; lpClass
0x18000346d  mov     [rsp+0B0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180003472  xor     r8d, r8d; Reserved
0x180003475  mov     [rsp+0B0h+samDesired], r12d; samDesired
0x18000347a  mov     rdx, rdi; lpSubKey
0x18000347d  mov     dword ptr [rsp+0B0h+phkResult], ecx; dwOptions
0x180003481  mov     rcx, rbx; hKey
0x180003484  call    cs:__imp_RegCreateKeyExA
0x18000348a  jmp     loc_180003403
```
