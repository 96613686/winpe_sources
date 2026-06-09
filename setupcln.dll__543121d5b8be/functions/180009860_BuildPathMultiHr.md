# BuildPathMultiHr

- ea: `0x180009860`
- end: `0x1800099ba`
- name: `BuildPathMultiHr`
- size: `346`
- prototype: `__int64 __fastcall(wchar_t **, unsigned int, const wchar_t *, const wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001200c`
- `0x1800123a0`

## callees

- `0x180009860`
- `0x18000a780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000991d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000991d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009931`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000994f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000998e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000994f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000998e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000995d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000999c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000995d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000999c`

## pseudocode

```c
__int64 __fastcall BuildPathMultiHr(wchar_t **a1, unsigned int a2, const wchar_t *a3, const wchar_t *a4, __int64 a5)
{
  unsigned int v6; // esi
  const wchar_t **v7; // r14
  wchar_t *v8; // rdi
  signed int v9; // ebx
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // eax
  const wchar_t *v13; // rdx
  wchar_t *v14; // rbp
  signed int v15; // eax
  bool v16; // sf
  signed int v17; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax

  if ( a1 )
  {
    v6 = 2;
    if ( a2 >= 2 )
    {
      v7 = (const wchar_t **)&a5;
      v8 = BuildPath(a3, a4);
      if ( v8 )
      {
        v9 = 0;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError < 0;
        if ( LastError > 0 )
          v11 = 1;
        if ( v11 )
        {
          v12 = GetLastError();
          v9 = v12;
          if ( v12 > 0 )
            v9 = (unsigned __int16)v12 | 0x80070000;
        }
        else
        {
          v9 = -2147467259;
        }
      }
      if ( a2 <= 2 )
      {
LABEL_27:
        if ( v9 >= 0 )
        {
          *a1 = v8;
          return (unsigned int)v9;
        }
      }
      else
      {
        while ( v9 >= 0 )
        {
          v13 = *v7++;
          v14 = BuildPath(v8, v13);
          if ( v14 )
          {
            v9 = 0;
          }
          else
          {
            v15 = GetLastError();
            v16 = v15 < 0;
            if ( v15 > 0 )
              v16 = 1;
            if ( v16 )
            {
              v17 = GetLastError();
              v9 = v17;
              if ( v17 > 0 )
                v9 = (unsigned __int16)v17 | 0x80070000;
            }
            else
            {
              v9 = -2147467259;
            }
          }
          if ( v8 )
          {
            ProcessHeap = GetProcessHeap();
            if ( HeapFree(ProcessHeap, 0, v8) )
              v8 = 0;
          }
          ++v6;
          if ( v9 < 0 )
            v14 = v8;
          v8 = v14;
          if ( v6 >= a2 )
            goto LABEL_27;
        }
      }
      if ( v8 )
      {
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v8);
      }
      return (unsigned int)v9;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180009860  mov     rax, rsp
0x180009863  mov     [rax+10h], edx
0x180009866  mov     [rax+18h], r8
0x18000986a  mov     [rax+20h], r9
0x18000986e  push    rbx
0x18000986f  push    rbp
0x180009870  push    rsi
0x180009871  push    rdi
0x180009872  push    r12
0x180009874  push    r14
0x180009876  push    r15
0x180009878  sub     rsp, 30h
0x18000987c  mov     r15, rcx
0x18000987f  mov     qword ptr [rax-48h], 0
0x180009887  lea     rcx, [rax+18h]
0x18000988b  test    r15, r15
0x18000988e  jz      loc_1800099A6
0x180009894  mov     esi, 2
0x180009899  cmp     edx, esi
0x18000989b  jb      loc_1800099A6
0x1800098a1  lea     r14, [rcx+10h]
0x1800098a5  mov     rcx, [rcx]; pszSrc
0x1800098a8  mov     rdx, [r14-8]; STRSAFE_PCNZWCH
0x1800098ac  call    BuildPath
0x1800098b1  mov     rdi, rax
0x1800098b4  mov     r12d, 80070000h
0x1800098ba  test    rax, rax
0x1800098bd  jz      short loc_1800098C3
0x1800098bf  xor     ebx, ebx
0x1800098c1  jmp     short loc_1800098F0
0x1800098c3  call    cs:__imp_GetLastError
0x1800098c9  test    eax, eax
0x1800098cb  jle     short loc_1800098D5
0x1800098cd  movzx   eax, ax
0x1800098d0  or      eax, r12d
0x1800098d3  test    eax, eax
0x1800098d5  jns     short loc_1800098EB
0x1800098d7  call    cs:__imp_GetLastError
0x1800098dd  mov     ebx, eax
0x1800098df  test    eax, eax
0x1800098e1  jle     short loc_1800098F0
0x1800098e3  movzx   ebx, ax
0x1800098e6  or      ebx, r12d
0x1800098e9  jmp     short loc_1800098F0
0x1800098eb  mov     ebx, 80004005h
0x1800098f0  cmp     [rsp+68h+arg_8], esi
0x1800098f4  jbe     loc_180009980
0x1800098fa  test    ebx, ebx
0x1800098fc  js      loc_180009989
0x180009902  mov     rdx, [r14]; STRSAFE_PCNZWCH
0x180009905  add     r14, 8
0x180009909  mov     rcx, rdi; pszSrc
0x18000990c  call    BuildPath
0x180009911  mov     rbp, rax
0x180009914  test    rax, rax
0x180009917  jz      short loc_18000991D
0x180009919  xor     ebx, ebx
0x18000991b  jmp     short loc_18000994A
0x18000991d  call    cs:__imp_GetLastError
0x180009923  test    eax, eax
0x180009925  jle     short loc_18000992F
0x180009927  movzx   eax, ax
0x18000992a  or      eax, r12d
0x18000992d  test    eax, eax
0x18000992f  jns     short loc_180009945
0x180009931  call    cs:__imp_GetLastError
0x180009937  mov     ebx, eax
0x180009939  test    eax, eax
0x18000993b  jle     short loc_18000994A
0x18000993d  movzx   ebx, ax
0x180009940  or      ebx, r12d
0x180009943  jmp     short loc_18000994A
0x180009945  mov     ebx, 80004005h
0x18000994a  test    rdi, rdi
0x18000994d  jz      short loc_18000996B
0x18000994f  call    cs:__imp_GetProcessHeap
0x180009955  mov     r8, rdi; lpMem
0x180009958  xor     edx, edx; dwFlags
0x18000995a  mov     rcx, rax; hHeap
0x18000995d  call    cs:__imp_HeapFree
0x180009963  xor     ecx, ecx
0x180009965  test    eax, eax
0x180009967  cmovnz  rdi, rcx
0x18000996b  inc     esi
0x18000996d  test    ebx, ebx
0x18000996f  cmovs   rbp, rdi
0x180009973  mov     rdi, rbp
0x180009976  cmp     esi, [rsp+68h+arg_8]
0x18000997a  jb      loc_1800098FA
0x180009980  test    ebx, ebx
0x180009982  js      short loc_180009989
0x180009984  mov     [r15], rdi
0x180009987  jmp     short loc_1800099A2
0x180009989  test    rdi, rdi
0x18000998c  jz      short loc_1800099A2
0x18000998e  call    cs:__imp_GetProcessHeap
0x180009994  mov     r8, rdi; lpMem
0x180009997  xor     edx, edx; dwFlags
0x180009999  mov     rcx, rax; hHeap
0x18000999c  call    cs:__imp_HeapFree
0x1800099a2  mov     eax, ebx
0x1800099a4  jmp     short loc_1800099AB
0x1800099a6  mov     eax, 80070057h
0x1800099ab  add     rsp, 30h
0x1800099af  pop     r15
0x1800099b1  pop     r14
0x1800099b3  pop     r12
0x1800099b5  pop     rdi
0x1800099b6  pop     rsi
0x1800099b7  pop     rbp
0x1800099b8  pop     rbx
0x1800099b9  retn
```
