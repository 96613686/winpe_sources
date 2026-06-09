# RegQueryValueWithAlloc

- ea: `0x140002090`
- end: `0x1400021ae`
- name: `RegQueryValueWithAlloc`
- size: `286`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, LPCWSTR lpValue@<rdx>, SIZE_T dwBytes)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400068a4`

## callees

- `0x140002090`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000212b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000212b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002197`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002197`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400020e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002163`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400020e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002163`

## pseudocode

```c
LSTATUS __fastcall RegQueryValueWithAlloc(HKEY hkey, LPCWSTR lpValue, int a3, _QWORD *a4, _DWORD *dwBytes)
{
  _DWORD *v5; // r14
  LSTATUS result; // eax
  void *pvData; // rbx
  LSTATUS v12; // edi
  DWORD pdwType; // [rsp+78h] [rbp+20h] BYREF

  v5 = dwBytes;
  *a4 = 0;
  *v5 = 0;
  pdwType = 0;
  LODWORD(dwBytes) = 0;
  result = RegGetValueW(hkey, 0, lpValue, 0xFFFFu, &pdwType, 0, (LPDWORD)&dwBytes);
  if ( !result )
  {
    if ( pdwType == a3 && (_DWORD)dwBytes )
    {
      pvData = HeapAlloc(g_hHeap, 0, (unsigned int)dwBytes);
      if ( pvData )
      {
        result = RegGetValueW(hkey, 0, lpValue, 0xFFFFu, &pdwType, pvData, (LPDWORD)&dwBytes);
        v12 = result;
        if ( result )
        {
          HeapFree(g_hHeap, 0, pvData);
          return v12;
        }
        else
        {
          *v5 = (_DWORD)dwBytes;
          *a4 = pvData;
        }
      }
      else
      {
        return 14;
      }
    }
    else
    {
      return 13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002090  mov     r11, rsp
0x140002093  mov     [r11+8], rbx
0x140002097  mov     [r11+10h], rbp
0x14000209b  push    rsi
0x14000209c  push    rdi
0x14000209d  push    r14
0x14000209f  sub     rsp, 40h
0x1400020a3  mov     r14, [rsp+58h+dwBytes]
0x1400020ab  lea     rax, [r11+28h]
0x1400020af  mov     [r11-28h], rax
0x1400020b3  mov     rbp, rcx
0x1400020b6  xor     ecx, ecx
0x1400020b8  lea     rax, [r11+20h]
0x1400020bc  mov     [r9], rcx
0x1400020bf  mov     ebx, r8d
0x1400020c2  mov     [r11-30h], rcx
0x1400020c6  mov     rsi, r9
0x1400020c9  mov     [r14], ecx
0x1400020cc  mov     rdi, rdx
0x1400020cf  mov     [rsp+58h+arg_18], ecx
0x1400020d3  mov     r8, rdx; lpValue
0x1400020d6  mov     [r11+28h], ecx
0x1400020da  mov     r9d, 0FFFFh; dwFlags
0x1400020e0  mov     rcx, rbp; hkey
0x1400020e3  mov     [r11-38h], rax
0x1400020e7  xor     edx, edx; lpSubKey
0x1400020e9  call    cs:__imp_RegGetValueW
0x1400020ef  test    eax, eax
0x1400020f1  jz      short loc_140002106
0x1400020f3  mov     rbx, [rsp+58h+arg_0]
0x1400020f8  mov     rbp, [rsp+58h+arg_8]
0x1400020fd  add     rsp, 40h
0x140002101  pop     r14
0x140002103  pop     rdi
0x140002104  pop     rsi
0x140002105  retn
0x140002106  cmp     [rsp+58h+arg_18], ebx
0x14000210a  jnz     loc_1400021A4
0x140002110  mov     eax, dword ptr [rsp+58h+dwBytes]
0x140002117  test    eax, eax
0x140002119  jz      loc_1400021A4
0x14000211f  mov     rcx, cs:g_hHeap; hHeap
0x140002126  mov     r8d, eax; dwBytes
0x140002129  xor     edx, edx; dwFlags
0x14000212b  call    cs:__imp_HeapAlloc
0x140002131  mov     rbx, rax
0x140002134  test    rax, rax
0x140002137  jz      short loc_140002181
0x140002139  lea     rax, [rsp+58h+dwBytes]
0x140002141  mov     r9d, 0FFFFh; dwFlags
0x140002147  mov     [rsp+58h+pcbData], rax; pcbData
0x14000214c  mov     r8, rdi; lpValue
0x14000214f  lea     rax, [rsp+58h+arg_18]
0x140002154  mov     [rsp+58h+pvData], rbx; pvData
0x140002159  xor     edx, edx; lpSubKey
0x14000215b  mov     [rsp+58h+pdwType], rax; pdwType
0x140002160  mov     rcx, rbp; hkey
0x140002163  call    cs:__imp_RegGetValueW
0x140002169  mov     edi, eax
0x14000216b  test    eax, eax
0x14000216d  jnz     short loc_14000218B
0x14000216f  mov     ecx, dword ptr [rsp+58h+dwBytes]
0x140002176  mov     [r14], ecx
0x140002179  mov     [rsi], rbx
0x14000217c  jmp     loc_1400020F3
0x140002181  mov     eax, 0Eh
0x140002186  jmp     loc_1400020F3
0x14000218b  mov     rcx, cs:g_hHeap; hHeap
0x140002192  mov     r8, rbx; lpMem
0x140002195  xor     edx, edx; dwFlags
0x140002197  call    cs:__imp_HeapFree
0x14000219d  mov     eax, edi
0x14000219f  jmp     loc_1400020F3
0x1400021a4  mov     eax, 0Dh
0x1400021a9  jmp     loc_1400020F3
```
