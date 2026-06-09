# mciReparseOpen(MCI_INTERNAL_OPEN_INFO *,uint,uint,ulong *,tagMCI_OPEN_PARMSW * *,uint)

- ea: `0x1800146cc`
- end: `0x18001482d`
- name: `?mciReparseOpen@@YAIPEAUMCI_INTERNAL_OPEN_INFO@@IIPEAKPEAPEAUtagMCI_OPEN_PARMSW@@I@Z`
- size: `353`
- prototype: `unsigned int __fastcall(struct MCI_INTERNAL_OPEN_INFO *, unsigned int, unsigned int, unsigned int *, struct tagMCI_OPEN_PARMSW **, MCIDEVICEID mciId)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180013f64`

## callees

- `0x1800127ac`
- `0x180013408`
- `0x18001381c`
- `0x1800146cc`
- `0x180014b54`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147af`

## pseudocode

```c
__int64 __fastcall mciReparseOpen(
        LPVOID *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        struct tagMCI_OPEN_PARMSW **a5,
        MCIDEVICEID mciId)
{
  unsigned int v6; // esi
  const WCHAR *CommandInTable; // rbp
  __int64 v12; // rax
  struct tagMCI_OPEN_PARMSW *v13; // rbx
  unsigned int v14; // ebp
  HANDLE v15; // rcx

  v6 = *a4;
  if ( a2 == -1 || (CommandInTable = FindCommandInTable(a2, wszOpen, 0)) == 0 )
  {
    CommandInTable = FindCommandInTable(a3, wszOpen, 0);
    if ( !CommandInTable )
      return *((unsigned int *)a1 + 6);
  }
  mciParserFree(a1[1]);
  a1[1] = 0;
  *a4 = 0;
  v12 = winmmAlloc(0xA0u);
  v13 = (struct tagMCI_OPEN_PARMSW *)v12;
  if ( !v12 )
    return 264;
  v14 = mciParseParams(2051, *a1, CommandInTable, a4, v12);
  if ( v14 )
  {
    mciCloseDevice(mciId, 0, 0);
    v15 = hHeap;
    a1[1] = 0;
    HeapFree(v15, 0, v13);
    return v14;
  }
  else
  {
    if ( (v6 & 0x2000) != 0 )
    {
      v13->lpstrDeviceType = (*a5)->lpstrDeviceType;
      *a4 |= 0x2000u;
    }
    if ( (v6 & 0x200) != 0 )
    {
      v13->lpstrElementName = (*a5)->lpstrElementName;
      *a4 |= 0x200u;
    }
    if ( (v6 & 0x400) != 0 )
    {
      v13->lpstrAlias = (*a5)->lpstrAlias;
      *a4 |= 0x400u;
    }
    if ( (v6 & 1) != 0 )
      v13->dwCallback = (*a5)->dwCallback;
    *a5 = v13;
    return 0;
  }
}

```

## disassembly

```asm
0x1800146cc  push    rbx
0x1800146ce  push    rbp
0x1800146cf  push    rsi
0x1800146d0  push    rdi
0x1800146d1  push    r14
0x1800146d3  push    r15
0x1800146d5  sub     rsp, 48h
0x1800146d9  mov     esi, [r9]
0x1800146dc  mov     rdi, r9
0x1800146df  mov     ebx, r8d
0x1800146e2  mov     eax, edx
0x1800146e4  mov     r15, rcx
0x1800146e7  cmp     edx, 0FFFFFFFFh
0x1800146ea  jz      short loc_180014705
0x1800146ec  xor     r8d, r8d
0x1800146ef  lea     rdx, ?wszOpen@@3PAGA; "open"
0x1800146f6  mov     ecx, eax
0x1800146f8  call    FindCommandInTable
0x1800146fd  mov     rbp, rax
0x180014700  test    rax, rax
0x180014703  jnz     short loc_180014727
0x180014705  xor     r8d, r8d
0x180014708  lea     rdx, ?wszOpen@@3PAGA; "open"
0x18001470f  mov     ecx, ebx
0x180014711  call    FindCommandInTable
0x180014716  mov     rbp, rax
0x180014719  test    rax, rax
0x18001471c  jnz     short loc_180014727
0x18001471e  mov     eax, [r15+18h]
0x180014722  jmp     loc_180014820
0x180014727  lea     r14, [r15+8]
0x18001472b  mov     rcx, [r14]; lpMem
0x18001472e  call    mciParserFree
0x180014733  mov     qword ptr [r14], 0
0x18001473a  mov     ecx, 0A0h; Size
0x18001473f  mov     dword ptr [rdi], 0
0x180014745  call    winmmAlloc
0x18001474a  mov     rbx, rax
0x18001474d  test    rax, rax
0x180014750  jnz     short loc_18001475C
0x180014752  mov     eax, 108h
0x180014757  jmp     loc_180014820
0x18001475c  mov     rdx, [r15]
0x18001475f  mov     r9, rdi
0x180014762  mov     [rsp+78h+var_40], 0
0x18001476b  mov     r8, rbp
0x18001476e  mov     [rsp+78h+var_48], r14
0x180014773  mov     ecx, 803h
0x180014778  mov     [rsp+78h+var_58], rbx
0x18001477d  call    mciParseParams
0x180014782  mov     ebp, eax
0x180014784  test    eax, eax
0x180014786  jz      short loc_1800147B9
0x180014788  mov     ecx, [rsp+78h+mciId]; mciId
0x18001478f  xor     r9d, r9d
0x180014792  xor     r8d, r8d; dwParam2
0x180014795  xor     edx, edx; dwParam1
0x180014797  call    mciCloseDevice
0x18001479c  mov     rcx, cs:hHeap; hHeap
0x1800147a3  mov     r8, rbx; lpMem
0x1800147a6  xor     edx, edx; dwFlags
0x1800147a8  mov     qword ptr [r14], 0
0x1800147af  call    cs:__imp_HeapFree
0x1800147b5  mov     eax, ebp
0x1800147b7  jmp     short loc_180014820
0x1800147b9  mov     rdx, [rsp+78h+arg_20]
0x1800147c1  mov     r8d, 2000h
0x1800147c7  test    r8d, esi
0x1800147ca  jz      short loc_1800147DA
0x1800147cc  mov     rax, [rdx]
0x1800147cf  mov     rcx, [rax+0Ch]
0x1800147d3  mov     [rbx+0Ch], rcx
0x1800147d7  or      [rdi], r8d
0x1800147da  mov     r8d, 200h
0x1800147e0  test    r8d, esi
0x1800147e3  jz      short loc_1800147F3
0x1800147e5  mov     rax, [rdx]
0x1800147e8  mov     rcx, [rax+14h]
0x1800147ec  mov     [rbx+14h], rcx
0x1800147f0  or      [rdi], r8d
0x1800147f3  mov     r8d, 400h
0x1800147f9  test    r8d, esi
0x1800147fc  jz      short loc_18001480C
0x1800147fe  mov     rax, [rdx]
0x180014801  mov     rcx, [rax+1Ch]
0x180014805  mov     [rbx+1Ch], rcx
0x180014809  or      [rdi], r8d
0x18001480c  test    sil, 1
0x180014810  jz      short loc_18001481B
0x180014812  mov     rax, [rdx]
0x180014815  mov     rcx, [rax]
0x180014818  mov     [rbx], rcx
0x18001481b  mov     [rdx], rbx
0x18001481e  xor     eax, eax
0x180014820  add     rsp, 48h
0x180014824  pop     r15
0x180014826  pop     r14
0x180014828  pop     rdi
0x180014829  pop     rsi
0x18001482a  pop     rbp
0x18001482b  pop     rbx
0x18001482c  retn
```
