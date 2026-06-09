# RegQueryValueWithAlloc

- ea: `0x1400021c0`
- end: `0x1400022f7`
- name: `RegQueryValueWithAlloc`
- size: `311`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, LPCWSTR lpValue@<rdx>, SIZE_T dwBytes)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140003470`
- `0x140006d84`

## callees

- `0x1400021c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002262`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002262`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400022da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400022da`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002219`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400022a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002219`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400022a0`

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
0x1400021c0  mov     r11, rsp
0x1400021c3  mov     [r11+8], rbx
0x1400021c7  mov     [r11+10h], rbp
0x1400021cb  push    rsi
0x1400021cc  push    rdi
0x1400021cd  push    r14
0x1400021cf  sub     rsp, 40h
0x1400021d3  mov     r14, [rsp+58h+dwBytes]
0x1400021db  lea     rax, [r11+28h]
0x1400021df  mov     [r11-28h], rax
0x1400021e3  mov     rbp, rcx
0x1400021e6  xor     ecx, ecx
0x1400021e8  lea     rax, [r11+20h]
0x1400021ec  mov     [r9], rcx
0x1400021ef  mov     ebx, r8d
0x1400021f2  mov     [r11-30h], rcx
0x1400021f6  mov     rsi, r9
0x1400021f9  mov     [r14], ecx
0x1400021fc  mov     rdi, rdx
0x1400021ff  mov     [rsp+58h+arg_18], ecx
0x140002203  mov     r8, rdx; lpValue
0x140002206  mov     [r11+28h], ecx
0x14000220a  mov     r9d, 0FFFFh; dwFlags
0x140002210  mov     rcx, rbp; hkey
0x140002213  mov     [r11-38h], rax
0x140002217  xor     edx, edx; lpSubKey
0x140002219  call    cs:__imp_RegGetValueW
0x140002220  nop     dword ptr [rax+rax+00h]
0x140002225  test    eax, eax
0x140002227  jz      short loc_14000223D
0x140002229  mov     rbx, [rsp+58h+arg_0]
0x14000222e  mov     rbp, [rsp+58h+arg_8]
0x140002233  add     rsp, 40h
0x140002237  pop     r14
0x140002239  pop     rdi
0x14000223a  pop     rsi
0x14000223b  retn
0x14000223d  cmp     [rsp+58h+arg_18], ebx
0x140002241  jnz     loc_1400022ED
0x140002247  mov     eax, dword ptr [rsp+58h+dwBytes]
0x14000224e  test    eax, eax
0x140002250  jz      loc_1400022ED
0x140002256  mov     rcx, cs:g_hHeap; hHeap
0x14000225d  mov     r8d, eax; dwBytes
0x140002260  xor     edx, edx; dwFlags
0x140002262  call    cs:__imp_HeapAlloc
0x140002269  nop     dword ptr [rax+rax+00h]
0x14000226e  mov     rbx, rax
0x140002271  test    rax, rax
0x140002274  jz      short loc_1400022C4
0x140002276  lea     rax, [rsp+58h+dwBytes]
0x14000227e  mov     r9d, 0FFFFh; dwFlags
0x140002284  mov     [rsp+58h+pcbData], rax; pcbData
0x140002289  mov     r8, rdi; lpValue
0x14000228c  lea     rax, [rsp+58h+arg_18]
0x140002291  mov     [rsp+58h+pvData], rbx; pvData
0x140002296  xor     edx, edx; lpSubKey
0x140002298  mov     [rsp+58h+pdwType], rax; pdwType
0x14000229d  mov     rcx, rbp; hkey
0x1400022a0  call    cs:__imp_RegGetValueW
0x1400022a7  nop     dword ptr [rax+rax+00h]
0x1400022ac  mov     edi, eax
0x1400022ae  test    eax, eax
0x1400022b0  jnz     short loc_1400022CE
0x1400022b2  mov     ecx, dword ptr [rsp+58h+dwBytes]
0x1400022b9  mov     [r14], ecx
0x1400022bc  mov     [rsi], rbx
0x1400022bf  jmp     loc_140002229
0x1400022c4  mov     eax, 0Eh
0x1400022c9  jmp     loc_140002229
0x1400022ce  mov     rcx, cs:g_hHeap; hHeap
0x1400022d5  mov     r8, rbx; lpMem
0x1400022d8  xor     edx, edx; dwFlags
0x1400022da  call    cs:__imp_HeapFree
0x1400022e1  nop     dword ptr [rax+rax+00h]
0x1400022e6  mov     eax, edi
0x1400022e8  jmp     loc_140002229
0x1400022ed  mov     eax, 0Dh
0x1400022f2  jmp     loc_140002229
```
