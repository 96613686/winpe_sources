# CRegistrySource::QueryValueString(ushort const *,ushort const *,ushort * *)

- ea: `0x1800075f0`
- end: `0x180007992`
- name: `?QueryValueString@CRegistrySource@@UEAAJPEBG0PEAPEAG@Z`
- size: `930`
- prototype: `int(CRegistrySource *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005da0`
- `0x180007120`
- `0x1800075f0`
- `0x1800079a0`
- `0x180008018`
- `0x1800083d0`
- `0x180066910`
- `0x18009341c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007812`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007676`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007676`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800077cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800077cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007933`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007973`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007933`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007973`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007757`

## pseudocode

```c
LSTATUS __fastcall CRegistrySource::QueryValueString(
        CRegistrySource *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  DWORD v5; // esi
  HKEY v8; // r15
  DWORD v9; // edi
  unsigned int v10; // eax
  unsigned __int64 v11; // rcx
  LSTATUS ValueW; // ebx
  LSTATUS v13; // eax
  unsigned __int64 v14; // r8
  __int64 v15; // rdx
  int v16; // r9d
  DWORD v17; // eax
  void **v18; // r15
  __int64 v19; // rax
  SIZE_T v21; // rdi
  void *v22; // rax
  void *v23; // rbx
  LSTATUS result; // eax
  int v25; // edi
  LSTATUS v26; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  void **v30; // [rsp+50h] [rbp-B0h]
  BYTE Data[2]; // [rsp+60h] [rbp-A0h] BYREF

  v30 = (void **)a4;
  v5 = 256;
  cbData = 256;
  Type = 0;
  v8 = (HKEY)*((_QWORD *)this + 6);
  v9 = 0;
  if ( !v8 )
  {
    LOWORD(ValueW) = 87;
    *a4 = 0;
    return (unsigned __int16)ValueW | 0x80070000;
  }
  if ( a2 && *a2 )
  {
    phkResult = 0;
    ValueW = RegOpenKeyExW(v8, a2, 0, 1u, &phkResult);
    if ( !ValueW )
    {
      ValueW = SHRegQueryValueW(phkResult, a3, Data, (__int64)&cbData);
      RegCloseKey(phkResult);
      v5 = cbData;
      v9 = Type;
    }
  }
  else
  {
    Type = 0;
    cbData = 256;
    v10 = RegQueryValueExW(v8, a3, 0, &Type, Data, &cbData);
    ValueW = v10;
    if ( v10 && v10 != 234 )
    {
      v9 = Type;
    }
    else
    {
      v9 = Type;
      switch ( Type )
      {
        case 1u:
          if ( v10 )
          {
            v11 = cbData + 2;
            if ( (unsigned int)v11 >= cbData )
            {
              cbData += 2;
            }
            else
            {
              cbData = -1;
              ValueW = 534;
            }
          }
          else
          {
            v14 = cbData;
            v15 = cbData >> 1;
            if ( !(_DWORD)v15 || *(_WORD *)&Data[2 * (unsigned int)(v15 - 1)] )
            {
              v16 = 1;
              if ( (unsigned int)(v15 + 1) <= 0x80 )
                *(_WORD *)&Data[2 * v15] = 0;
              else
                ValueW = 234;
            }
            else
            {
              v16 = 0;
            }
            v17 = v14;
            v11 = 2LL * (unsigned int)(v15 + v16);
            if ( v14 <= v11 )
              v17 = 2 * (v15 + v16);
            cbData = v17;
          }
          break;
        case 2u:
          ValueW = NullTerminateRegExpandSzStringW(v8, (__int64)&cbData, 256, v10);
          v9 = 1;
          break;
        case 7u:
          v13 = NullTerminateRegMultiSzStringW(Data, &cbData, 256, v10);
          v9 = Type;
          ValueW = v13;
          break;
      }
    }
    v5 = cbData;
    Type = v9;
  }
  v18 = v30;
  *v30 = 0;
  if ( ValueW )
  {
    if ( ValueW == 234 )
    {
      result = CTCoAllocPolicy::Alloc((void *)v11, 1u, v5, v18);
      v25 = result;
      if ( result < 0 )
        return result;
      v26 = SHRegGetValueW(*((HKEY *)this + 6), a2, a3, 0xFFFF, &Type, *v18, &cbData);
      ValueW = v26;
      if ( Type != 1 )
      {
        LOWORD(ValueW) = 1629;
        CoTaskMemFree(*v18);
        *v18 = 0;
        return (unsigned __int16)ValueW | 0x80070000;
      }
      if ( !v26 )
        return v25;
      CoTaskMemFree(*v18);
      *v18 = 0;
    }
    if ( ValueW <= 0 )
      return ValueW;
    return (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v9 != 1 )
    return -2147023267;
  if ( !a3 && !*(_WORD *)Data )
    return -2147024894;
  v19 = -1;
  while ( *(_WORD *)&Data[2 * v19++ + 2] != 0 )
    ;
  v21 = (unsigned int)(2 * v19 + 2);
  v22 = CoTaskMemAlloc(v21);
  v23 = v22;
  if ( !v22 )
    return -2147024882;
  memcpy_0(v22, Data, v21);
  result = 0;
  *v18 = v23;
  return result;
}

```

## disassembly

```asm
0x1800075f0  push    rbp
0x1800075f2  push    rbx
0x1800075f3  push    rsi
0x1800075f4  push    rdi
0x1800075f5  push    r12
0x1800075f7  push    r13
0x1800075f9  push    r14
0x1800075fb  push    r15
0x1800075fd  lea     rbp, [rsp-78h]
0x180007602  sub     rsp, 178h
0x180007609  mov     rax, cs:__security_cookie
0x180007610  xor     rax, rsp
0x180007613  mov     [rbp+0B0h+var_50], rax
0x180007617  mov     r13, rcx
0x18000761a  mov     [rsp+1B0h+var_160], r9
0x18000761f  xor     ecx, ecx
0x180007621  mov     esi, 100h
0x180007626  mov     r14, r8
0x180007629  mov     [rsp+1B0h+cbData], esi
0x18000762d  mov     r12, rdx
0x180007630  mov     [rsp+1B0h+Type], ecx
0x180007634  mov     r15, [r13+30h]
0x180007638  mov     edi, ecx
0x18000763a  test    r15, r15
0x18000763d  jz      loc_180007985
0x180007643  test    rdx, rdx
0x180007646  jnz     loc_1800077AB
0x18000764c  lea     rax, [rsp+1B0h+cbData]
0x180007651  mov     [rsp+1B0h+Type], ecx
0x180007655  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x18000765a  lea     r9, [rsp+1B0h+Type]; lpType
0x18000765f  lea     rax, [rsp+1B0h+Data]
0x180007664  mov     [rsp+1B0h+cbData], esi
0x180007668  xor     r8d, r8d; lpReserved
0x18000766b  mov     [rsp+1B0h+lpData], rax; lpData
0x180007670  mov     rdx, r14; lpValueName
0x180007673  mov     rcx, r15; hKey
0x180007676  call    cs:__imp_RegQueryValueExW
0x18000767c  mov     ebx, eax
0x18000767e  test    eax, eax
0x180007680  jz      short loc_18000768D
0x180007682  cmp     eax, 0EAh
0x180007687  jnz     loc_180007825
0x18000768d  mov     edi, [rsp+1B0h+Type]
0x180007691  mov     eax, edi
0x180007693  sub     eax, 1
0x180007696  jz      short loc_1800076C3
0x180007698  sub     eax, 1
0x18000769b  jz      loc_18000788B
0x1800076a1  cmp     eax, 5
0x1800076a4  jnz     short loc_180007703
0x1800076a6  mov     r9d, ebx
0x1800076a9  lea     rdx, [rsp+1B0h+cbData]
0x1800076ae  mov     r8d, esi
0x1800076b1  lea     rcx, [rsp+1B0h+Data]
0x1800076b6  call    NullTerminateRegMultiSzStringW
0x1800076bb  mov     edi, [rsp+1B0h+Type]
0x1800076bf  mov     ebx, eax
0x1800076c1  jmp     short loc_180007703
0x1800076c3  test    ebx, ebx
0x1800076c5  jnz     loc_18000785E
0x1800076cb  mov     r8d, [rsp+1B0h+cbData]
0x1800076d0  mov     edx, r8d
0x1800076d3  shr     edx, 1
0x1800076d5  cmp     edx, 1
0x1800076d8  jb      loc_1800078BE
0x1800076de  lea     eax, [rdx-1]
0x1800076e1  cmp     word ptr [rsp+rax*2+1B0h+Data], bx
0x1800076e6  jnz     loc_1800078BE
0x1800076ec  xor     r9d, r9d
0x1800076ef  lea     ecx, [rdx+r9]
0x1800076f3  mov     rax, r8
0x1800076f6  add     rcx, rcx; void *
0x1800076f9  cmp     r8, rcx
0x1800076fc  cmovbe  eax, ecx
0x1800076ff  mov     [rsp+1B0h+cbData], eax
0x180007703  mov     esi, [rsp+1B0h+cbData]
0x180007707  mov     [rsp+1B0h+cbData], esi
0x18000770b  mov     [rsp+1B0h+Type], edi
0x18000770f  mov     r15, [rsp+1B0h+var_160]
0x180007714  mov     qword ptr [r15], 0
0x18000771b  test    ebx, ebx
0x18000771d  jnz     short loc_18000778E
0x18000771f  cmp     edi, 1
0x180007722  jnz     loc_180007961
0x180007728  test    r14, r14
0x18000772b  jz      loc_180007848
0x180007731  lea     rcx, [rsp+1B0h+Data]
0x180007736  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000773d  nop     dword ptr [rax]
0x180007740  cmp     word ptr [rcx+rax*2+2], 0
0x180007746  lea     rax, [rax+1]
0x18000774a  jnz     short loc_180007740
0x18000774c  lea     eax, ds:2[rax*2]
0x180007753  mov     ecx, eax; cb
0x180007755  mov     edi, eax
0x180007757  call    cs:__imp_CoTaskMemAlloc
0x18000775d  mov     rbx, rax
0x180007760  test    rax, rax
0x180007763  jnz     loc_18000782E
0x180007769  mov     eax, 8007000Eh
0x18000776e  mov     rcx, [rbp+0B0h+var_50]
0x180007772  xor     rcx, rsp; StackCookie
0x180007775  call    __security_check_cookie
0x18000777a  add     rsp, 178h
0x180007781  pop     r15
0x180007783  pop     r14
0x180007785  pop     r13
0x180007787  pop     r12
0x180007789  pop     rdi
0x18000778a  pop     rsi
0x18000778b  pop     rbx
0x18000778c  pop     rbp
0x18000778d  retn
0x18000778e  cmp     ebx, 0EAh
0x180007794  jz      loc_1800078D8
0x18000779a  test    ebx, ebx
0x18000779c  jle     short loc_1800077A7
0x18000779e  movzx   ebx, bx
0x1800077a1  or      ebx, 80070000h
0x1800077a7  mov     eax, ebx
0x1800077a9  jmp     short loc_18000776E
0x1800077ab  cmp     [rdx], cx
0x1800077ae  jz      loc_18000764C
0x1800077b4  mov     [rsp+1B0h+phkResult], rcx
0x1800077b9  lea     rax, [rsp+1B0h+phkResult]
0x1800077be  mov     rcx, r15; hKey
0x1800077c1  mov     [rsp+1B0h+lpData], rax; phkResult
0x1800077c6  mov     r9d, 1; samDesired
0x1800077cc  xor     r8d, r8d; ulOptions
0x1800077cf  call    cs:__imp_RegOpenKeyExW
0x1800077d5  mov     ebx, eax
0x1800077d7  test    eax, eax
0x1800077d9  jnz     loc_18000770F
0x1800077df  mov     rcx, [rsp+1B0h+phkResult]; hKey
0x1800077e4  lea     rax, [rsp+1B0h+cbData]
0x1800077e9  mov     [rsp+1B0h+lpcbData], rax; __int64
0x1800077ee  lea     r9, [rsp+1B0h+Type]
0x1800077f3  lea     rax, [rsp+1B0h+Data]
0x1800077f8  mov     r8d, 0FFFFh
0x1800077fe  mov     rdx, r14; lpValueName
0x180007801  mov     [rsp+1B0h+lpData], rax; LPBYTE
0x180007806  call    _SHRegQueryValueW
0x18000780b  mov     rcx, [rsp+1B0h+phkResult]; hKey
0x180007810  mov     ebx, eax
0x180007812  call    cs:__imp_RegCloseKey
0x180007818  mov     esi, [rsp+1B0h+cbData]
0x18000781c  mov     edi, [rsp+1B0h+Type]
0x180007820  jmp     loc_18000770F
0x180007825  mov     edi, [rsp+1B0h+Type]
0x180007829  jmp     loc_180007703
0x18000782e  mov     r8, rdi; Size
0x180007831  lea     rdx, [rsp+1B0h+Data]; Src
0x180007836  mov     rcx, rbx; void *
0x180007839  call    memcpy_0
0x18000783e  xor     eax, eax
0x180007840  mov     [r15], rbx
0x180007843  jmp     loc_18000776E
0x180007848  cmp     word ptr [rsp+1B0h+Data], 0
0x18000784e  jnz     loc_180007731
0x180007854  mov     eax, 80070002h
0x180007859  jmp     loc_18000776E
0x18000785e  cmp     ebx, 0EAh
0x180007864  jnz     loc_180007703
0x18000786a  mov     eax, [rsp+1B0h+cbData]
0x18000786e  lea     ecx, [rax+2]
0x180007871  cmp     ecx, eax
0x180007873  jnb     loc_180007958
0x180007879  mov     [rsp+1B0h+cbData], 0FFFFFFFFh
0x180007881  mov     ebx, 216h
0x180007886  jmp     loc_180007703
0x18000788b  mov     dword ptr [rsp+1B0h+pcbData], ebx; int
0x18000788f  lea     rax, [rsp+1B0h+cbData]
0x180007894  mov     dword ptr [rsp+1B0h+lpcbData], esi; int
0x180007898  lea     r9, [rsp+1B0h+Data]
0x18000789d  lea     r8, [rsp+1B0h+Type]
0x1800078a2  mov     [rsp+1B0h+lpData], rax; __int64
0x1800078a7  mov     rdx, r14
0x1800078aa  mov     rcx, r15; hKey
0x1800078ad  call    NullTerminateRegExpandSzStringW
0x1800078b2  mov     ebx, eax
0x1800078b4  mov     edi, 1
0x1800078b9  jmp     loc_180007703
0x1800078be  lea     eax, [rdx+1]
0x1800078c1  mov     r9d, 1
0x1800078c7  cmp     eax, 80h
0x1800078cc  jbe     short loc_18000794C
0x1800078ce  mov     ebx, 0EAh
0x1800078d3  jmp     loc_1800076EF
0x1800078d8  mov     r8d, esi; unsigned __int64
0x1800078db  mov     r9, r15; void **
0x1800078de  mov     edx, 1; unsigned int
0x1800078e3  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800078e8  mov     edi, eax
0x1800078ea  test    eax, eax
0x1800078ec  js      loc_18000776E
0x1800078f2  mov     rcx, [r15]
0x1800078f5  lea     rax, [rsp+1B0h+cbData]
0x1800078fa  mov     [rsp+1B0h+pcbData], rax; pcbData
0x1800078ff  mov     r9d, 0FFFFh; srrfFlags
0x180007905  mov     [rsp+1B0h+lpcbData], rcx; pvData
0x18000790a  lea     rax, [rsp+1B0h+Type]
0x18000790f  mov     rcx, [r13+30h]; hkey
0x180007913  mov     r8, r14; pszValue
0x180007916  mov     rdx, r12; pszSubKey
0x180007919  mov     [rsp+1B0h+lpData], rax; pdwType
0x18000791e  call    SHRegGetValueW
0x180007923  cmp     [rsp+1B0h+Type], 1
0x180007928  mov     ebx, eax
0x18000792a  jnz     short loc_18000796B
0x18000792c  test    eax, eax
0x18000792e  jz      short loc_180007945
0x180007930  mov     rcx, [r15]; pv
0x180007933  call    cs:__imp_CoTaskMemFree
0x180007939  mov     qword ptr [r15], 0
0x180007940  jmp     loc_18000779A
0x180007945  mov     eax, edi
0x180007947  jmp     loc_18000776E
0x18000794c  xor     eax, eax
0x18000794e  mov     word ptr [rsp+rdx*2+1B0h+Data], ax
0x180007953  jmp     loc_1800076EF
0x180007958  mov     [rsp+1B0h+cbData], ecx
0x18000795c  jmp     loc_180007703
0x180007961  mov     eax, 8007065Dh
0x180007966  jmp     loc_18000776E
0x18000796b  mov     rcx, [r15]; pv
0x18000796e  mov     ebx, 65Dh
0x180007973  call    cs:__imp_CoTaskMemFree
0x180007979  mov     qword ptr [r15], 0
0x180007980  jmp     loc_18000779E
0x180007985  mov     ebx, 57h ; 'W'
0x18000798a  mov     [r9], rcx
0x18000798d  jmp     loc_18000779E
```
