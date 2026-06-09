# CSpDynamicString::operator=(ushort const *)

- ea: `0x18000cdb0`
- end: `0x18000cf02`
- name: `??4CSpDynamicString@@QEAAPEAGPEBG@Z`
- size: `338`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `58`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bb20`
- `0x180012fe0`
- `0x180013470`
- `0x180018530`
- `0x18001a074`
- `0x18001cfdc`
- `0x180055344`
- `0x180058120`
- `0x18005d5a8`
- `0x18006d428`
- `0x18006d818`
- `0x1800ae7cc`
- `0x1800b3604`
- `0x1800bd214`
- `0x1800bd820`
- `0x1800c4230`
- `0x1800dfe50`
- `0x1800e0e48`
- `0x1800e2adc`
- `0x1800e2d10`
- `0x1800e2f60`
- `0x1800e33c0`
- `0x1800ebf18`
- `0x1800ec00c`
- `0x1800ecde0`
- `0x1800eea28`
- `0x1800eed80`
- `0x1800ef504`
- `0x1800fb620`
- `0x1800fbae4`
- `0x1800fc48c`
- `0x1801057b0`
- `0x18010583c`
- `0x180105b30`
- `0x1801070c0`
- `0x180125d50`
- `0x180127b64`
- `0x180128720`
- `0x18012d134`
- `0x180130340`
- `0x1801309e0`
- `0x18014ad50`
- `0x18014b2b0`
- `0x180156e28`
- `0x18016ed70`
- `0x18016efc4`
- `0x180170740`
- `0x180174430`
- `0x18017abbc`
- `0x18017ad30`

## callees

- `0x18000cdb0`
- `0x18007d7b1`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000cde4`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000cde4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cdd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cdd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cec4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ced1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cec4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ced1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce84`

## pseudocode

```c
LPVOID __fastcall CSpDynamicString::operator=(LPVOID *a1, _WORD *a2)
{
  const void *v2; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v6; // rax
  SIZE_T v7; // rax
  unsigned __int64 v8; // r8
  _DWORD *v9; // rcx
  unsigned __int64 v10; // r9
  __int64 v11; // rbx
  SIZE_T v12; // rcx
  LPVOID v13; // rax

  v2 = *a1;
  if ( a2 == *a1 )
    return *a1;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = HeapSize(ProcessHeap, 0, v2);
    if ( v6 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v7 = v6 >> 1;
      v8 = v7 - 1;
      if ( v7 - 1 < 8 )
      {
        if ( v7 == 1 )
          goto LABEL_8;
        v10 = 0;
      }
      else
      {
        v9 = *a1;
        if ( *a1 > a1 || (v10 = 0, v8 = 8, (LPVOID *)((char *)v9 + 14) < a1) )
        {
          *v9 = -559030611;
          v9[1] = -559030611;
          v9[2] = -559030611;
          v9[3] = -559030611;
          goto LABEL_8;
        }
      }
      do
        *((_WORD *)*a1 + v10++) = -8531;
      while ( v10 < v8 );
    }
LABEL_8:
    CoTaskMemFree(*a1);
    *a1 = 0;
  }
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    if ( (unsigned int)v11 >= 0x4FFFFFFF || (v12 = 2LL * (unsigned int)(v11 + 1), v12 <= (unsigned int)v11) )
    {
      SetLastError(0x216u);
    }
    else
    {
      v13 = CoTaskMemAlloc(v12);
      *a1 = v13;
      if ( v13 )
      {
        *((_WORD *)v13 + (unsigned int)v11) = 0;
        memcpy_0(*a1, a2, 2 * v11);
      }
      else
      {
        SetLastError(0xEu);
      }
    }
  }
  return *a1;
}

```

## disassembly

```asm
0x18000cdb0  mov     [rsp+arg_8], rbx
0x18000cdb5  mov     [rsp+arg_10], rsi
0x18000cdba  push    rdi
0x18000cdbb  sub     rsp, 20h
0x18000cdbf  mov     rbx, [rcx]
0x18000cdc2  mov     rdi, rdx
0x18000cdc5  mov     rsi, rcx
0x18000cdc8  cmp     rdx, rbx
0x18000cdcb  jz      loc_18000CEFD
0x18000cdd1  test    rbx, rbx
0x18000cdd4  jz      short loc_18000CE4E
0x18000cdd6  call    cs:__imp_GetProcessHeap
0x18000cddc  mov     r8, rbx; lpMem
0x18000cddf  xor     edx, edx; dwFlags
0x18000cde1  mov     rcx, rax; hHeap
0x18000cde4  call    cs:__imp_HeapSize
0x18000cdea  lea     rcx, [rax-3]
0x18000cdee  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x18000cdf2  ja      short loc_18000CE3E
0x18000cdf4  shr     rax, 1
0x18000cdf7  lea     r8, [rax-1]
0x18000cdfb  cmp     r8, 8
0x18000cdff  jb      loc_18000CED9
0x18000ce05  mov     rcx, [rsi]
0x18000ce08  cmp     rcx, rsi
0x18000ce0b  ja      short loc_18000CE23
0x18000ce0d  xor     r9d, r9d
0x18000ce10  lea     rax, [rcx+0Eh]
0x18000ce14  mov     r8d, 8
0x18000ce1a  cmp     rax, rsi
0x18000ce1d  jnb     loc_18000CEE5
0x18000ce23  mov     dword ptr [rcx], 0DEADDEADh
0x18000ce29  mov     dword ptr [rcx+4], 0DEADDEADh
0x18000ce30  mov     dword ptr [rcx+8], 0DEADDEADh
0x18000ce37  mov     dword ptr [rcx+0Ch], 0DEADDEADh
0x18000ce3e  mov     rcx, [rsi]; pv
0x18000ce41  call    cs:__imp_CoTaskMemFree
0x18000ce47  mov     qword ptr [rsi], 0
0x18000ce4e  test    rdi, rdi
0x18000ce51  jz      short loc_18000CEAC
0x18000ce53  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ce5a  nop     word ptr [rax+rax+00h]
0x18000ce60  inc     rbx
0x18000ce63  cmp     word ptr [rdi+rbx*2], 0
0x18000ce68  jnz     short loc_18000CE60
0x18000ce6a  mov     [rsp+28h+arg_0], rbp
0x18000ce6f  cmp     ebx, 4FFFFFFFh
0x18000ce75  jnb     short loc_18000CECC
0x18000ce77  lea     ecx, [rbx+1]
0x18000ce7a  mov     ebp, ebx
0x18000ce7c  add     rcx, rcx; cb
0x18000ce7f  cmp     rcx, rbp
0x18000ce82  jbe     short loc_18000CECC
0x18000ce84  call    cs:__imp_CoTaskMemAlloc
0x18000ce8a  mov     [rsi], rax
0x18000ce8d  test    rax, rax
0x18000ce90  jz      short loc_18000CEBF
0x18000ce92  xor     ecx, ecx
0x18000ce94  lea     r8, [rbx+rbx]; Size
0x18000ce98  mov     [rax+rbp*2], cx
0x18000ce9c  mov     rdx, rdi; Src
0x18000ce9f  mov     rcx, [rsi]; void *
0x18000cea2  call    memcpy_0
0x18000cea7  mov     rbp, [rsp+28h+arg_0]
0x18000ceac  mov     rax, [rsi]
0x18000ceaf  mov     rbx, [rsp+28h+arg_8]
0x18000ceb4  mov     rsi, [rsp+28h+arg_10]
0x18000ceb9  add     rsp, 20h
0x18000cebd  pop     rdi
0x18000cebe  retn
0x18000cebf  mov     ecx, 0Eh; dwErrCode
0x18000cec4  call    cs:__imp_SetLastError
0x18000ceca  jmp     short loc_18000CEA7
0x18000cecc  mov     ecx, 216h; dwErrCode
0x18000ced1  call    cs:__imp_SetLastError
0x18000ced7  jmp     short loc_18000CEA7
0x18000ced9  test    r8, r8
0x18000cedc  jz      loc_18000CE3E
0x18000cee2  xor     r9d, r9d
0x18000cee5  mov     rax, [rsi]
0x18000cee8  mov     word ptr [rax+r9*2], 0DEADh
0x18000ceef  inc     r9
0x18000cef2  cmp     r9, r8
0x18000cef5  jnb     loc_18000CE3E
0x18000cefb  jmp     short loc_18000CEE5
0x18000cefd  mov     rax, rbx
0x18000cf00  jmp     short loc_18000CEAF
```
