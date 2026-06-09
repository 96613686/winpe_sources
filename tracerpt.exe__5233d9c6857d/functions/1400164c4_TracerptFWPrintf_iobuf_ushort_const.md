# TracerptFWPrintf(_iobuf *,ushort const *,...)

- ea: `0x1400164c4`
- end: `0x1400166cc`
- name: `?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ`
- size: `520`
- prototype: `unsigned int(struct _iobuf *, const unsigned __int16 *, ...)`
- caller_count: `55`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000bec0`
- `0x14000bfe4`
- `0x14000c298`
- `0x14000c964`
- `0x14000ce24`
- `0x14000d174`
- `0x14000d4a8`
- `0x140011ff8`
- `0x1400120f4`
- `0x14001232c`
- `0x1400131c8`
- `0x1400137b8`
- `0x1400140f8`
- `0x140014218`
- `0x1400144c4`
- `0x1400145a0`
- `0x14001489c`
- `0x140014b98`
- `0x140014ccc`
- `0x140014e98`
- `0x1400155e0`
- `0x140015974`
- `0x140016ae0`
- `0x140018d04`
- `0x1400192b4`
- `0x14001f330`
- `0x14001f4ac`
- `0x14001f7d8`
- `0x14001f8d8`
- `0x14001fa40`
- `0x14001fb68`
- `0x14001fd7c`
- `0x140020310`
- `0x140020748`
- `0x1400208e4`
- `0x140021184`
- `0x140021ff4`
- `0x140022480`
- `0x1400268c8`
- `0x140026d88`
- `0x140027630`
- `0x140027de4`
- `0x1400281f0`
- `0x14002ac00`
- `0x14002ae38`
- `0x14002af78`
- `0x14002b158`
- `0x14002b2d4`
- `0x14002b4b0`
- `0x14002b818`

## callees

- `0x140015ee0`
- `0x1400164c4`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x14001654d`
- `msvcrt!_vsnprintf` at `0x14001654d`
- `msvcrt!_vsnwprintf` at `0x14001663c`
- `msvcrt!_vsnwprintf` at `0x14001663c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400165e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400165fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400165e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400165fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400165d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400165ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400165d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400165ec`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001658f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001667e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001658f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001667e`

## pseudocode

```c
__int64 TracerptFWPrintf(struct _iobuf *a1, wchar_t *a2, ...)
{
  char v3; // bp
  char *v4; // rsi
  int *p_cnt; // r15
  __int64 flag; // rcx
  unsigned __int64 v7; // rdi
  _BYTE *v8; // r14
  size_t v9; // rdi
  int v10; // eax
  bool v11; // zf
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  HANDLE v17; // rax
  int *v18; // r14
  __int64 v19; // rcx
  char *v20; // rsi
  size_t v21; // rdi
  int v22; // eax
  int v23; // ecx
  __int64 v24; // rcx
  DWORD NumberOfBytesWritten[22]; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v26; // [rsp+98h] [rbp+10h]
  va_list va; // [rsp+A0h] [rbp+18h] BYREF

  va_start(va, a2);
  v26 = a2;
  *(_QWORD *)NumberOfBytesWritten = 0;
  v3 = 0;
  if ( !LOBYTE(a1[1365]._charbuf) )
  {
    v4 = (char *)ConvertWideCharToMultiByte(a2);
    if ( !v4 )
      return 0;
    p_cnt = &a1->_cnt;
    while ( 1 )
    {
      flag = (unsigned int)a1[1365]._flag;
      v7 = (unsigned int)(0x10000 - flag);
      if ( (_DWORD)flag == 0x10000 )
        goto LABEL_14;
      v8 = (char *)p_cnt + flag;
      if ( v7 > 0x7FFFFFFF )
      {
        *v8 = 0;
        goto LABEL_14;
      }
      v9 = v7 - 1;
      v10 = _vsnprintf((char *const)p_cnt + flag, v9, v4, va);
      if ( v10 < 0 || (v11 = v10 == v9, v10 > v9) )
      {
        v12 = -2147024774;
      }
      else
      {
        v12 = 0;
        if ( !v11 )
          goto LABEL_13;
      }
      v8[v9] = 0;
LABEL_13:
      if ( v12 >= 0 )
      {
        v13 = (unsigned int)a1[1365]._flag;
        v14 = -1;
        do
          ++v14;
        while ( *((_BYTE *)&a1->_cnt + v13 + v14) );
        NumberOfBytesWritten[0] = v14;
        a1[1365]._flag = v13 + v14;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
        return NumberOfBytesWritten[0];
      }
LABEL_14:
      if ( v3 )
      {
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v4);
        return 0;
      }
      WriteFile(a1->_ptr, &a1->_cnt, a1[1365]._flag, NumberOfBytesWritten, 0);
      v3 = 1;
      a1[1365]._file += NumberOfBytesWritten[0];
      a1[1365]._flag = 0;
    }
  }
  v18 = &a1->_cnt;
  while ( 1 )
  {
    v19 = (unsigned int)a1[1365]._flag;
    if ( !((unsigned __int64)(unsigned int)(0x10000 - v19) >> 1) )
      goto LABEL_30;
    v20 = (char *)v18 + v19;
    v21 = ((unsigned __int64)(unsigned int)(0x10000 - v19) >> 1) - 1;
    v22 = _vsnwprintf((wchar_t *)((char *)v18 + v19), v21, a2, va);
    if ( v22 < 0 || v22 > v21 )
    {
      v23 = -2147024774;
    }
    else
    {
      v23 = 0;
      if ( v22 != v21 )
        goto LABEL_29;
    }
    *(_WORD *)&v20[2 * v21] = 0;
LABEL_29:
    if ( v23 >= 0 )
      break;
LABEL_30:
    if ( v3 )
      return 0;
    WriteFile(a1->_ptr, v18, a1[1365]._flag, NumberOfBytesWritten, 0);
    v3 = 1;
    a1[1365]._file += NumberOfBytesWritten[0];
    a2 = (wchar_t *)v26;
    a1[1365]._flag = 0;
  }
  v24 = (unsigned int)a1[1365]._flag;
  result = -1;
  do
    ++result;
  while ( *(_WORD *)((char *)&a1->_cnt + 2 * result + v24) );
  a1[1365]._flag = v24 + 2 * result;
  return result;
}

```

## disassembly

```asm
0x1400164c4  mov     rax, rsp
0x1400164c7  mov     [rax+10h], rdx
0x1400164cb  mov     [rax+18h], r8
0x1400164cf  mov     [rax+20h], r9
0x1400164d3  push    rbx
0x1400164d4  push    rbp
0x1400164d5  push    rsi
0x1400164d6  push    rdi
0x1400164d7  push    r12
0x1400164d9  push    r13
0x1400164db  push    r14
0x1400164dd  push    r15
0x1400164df  sub     rsp, 48h
0x1400164e3  xor     r12d, r12d
0x1400164e6  lea     r13, [rax+18h]
0x1400164ea  mov     rbx, rcx
0x1400164ed  mov     [rax-58h], r12
0x1400164f1  mov     bpl, r12b
0x1400164f4  mov     [rax-58h], r12d
0x1400164f8  cmp     [rcx+10010h], r12b
0x1400164ff  jnz     loc_140016613
0x140016505  mov     rcx, rdx; Src
0x140016508  call    ConvertWideCharToMultiByte
0x14001650d  mov     rsi, rax
0x140016510  test    rax, rax
0x140016513  jz      loc_140016600
0x140016519  lea     r15, [rbx+8]
0x14001651d  mov     ecx, [rbx+10008h]
0x140016523  mov     edi, 10000h
0x140016528  sub     edi, ecx
0x14001652a  jz      short loc_140016573
0x14001652c  lea     r14, [r15+rcx]
0x140016530  cmp     rdi, 7FFFFFFFh
0x140016537  jbe     short loc_14001653E
0x140016539  mov     [r14], r12b
0x14001653c  jmp     short loc_140016573
0x14001653e  dec     rdi
0x140016541  mov     r9, r13; ArgList
0x140016544  mov     rdx, rdi; BufferCount
0x140016547  mov     r8, rsi; Format
0x14001654a  mov     rcx, r14; Buffer
0x14001654d  call    cs:__imp__vsnprintf
0x140016553  test    eax, eax
0x140016555  js      short loc_140016566
0x140016557  movsxd  rcx, eax
0x14001655a  cmp     rcx, rdi
0x14001655d  ja      short loc_140016566
0x14001655f  mov     eax, r12d
0x140016562  jnz     short loc_14001656F
0x140016564  jmp     short loc_14001656B
0x140016566  mov     eax, 8007007Ah
0x14001656b  mov     [rdi+r14], r12b
0x14001656f  test    eax, eax
0x140016571  jns     short loc_1400165AE
0x140016573  test    bpl, bpl
0x140016576  jnz     short loc_1400165EC
0x140016578  mov     r8d, [rbx+10008h]; nNumberOfBytesToWrite
0x14001657f  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140016584  mov     rcx, [rbx]; hFile
0x140016587  mov     rdx, r15; lpBuffer
0x14001658a  mov     [rsp+88h+lpOverlapped], r12; lpOverlapped
0x14001658f  call    cs:__imp_WriteFile
0x140016595  mov     eax, [rsp+88h+NumberOfBytesWritten]
0x140016599  mov     bpl, 1
0x14001659c  add     [rbx+1000Ch], eax
0x1400165a2  mov     [rbx+10008h], r12d
0x1400165a9  jmp     loc_14001651D
0x1400165ae  mov     ecx, [rbx+10008h]
0x1400165b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400165b8  lea     rdx, [rcx+rbx]
0x1400165bc  inc     rax
0x1400165bf  cmp     [rdx+rax+8], r12b
0x1400165c4  jnz     short loc_1400165BC
0x1400165c6  mov     [rsp+88h+NumberOfBytesWritten], eax
0x1400165ca  add     eax, ecx
0x1400165cc  mov     [rbx+10008h], eax
0x1400165d2  call    cs:__imp_GetProcessHeap
0x1400165d8  mov     r8, rsi; lpMem
0x1400165db  xor     edx, edx; dwFlags
0x1400165dd  mov     rcx, rax; hHeap
0x1400165e0  call    cs:__imp_HeapFree
0x1400165e6  mov     eax, [rsp+88h+NumberOfBytesWritten]
0x1400165ea  jmp     short loc_140016602
0x1400165ec  call    cs:__imp_GetProcessHeap
0x1400165f2  mov     r8, rsi; lpMem
0x1400165f5  xor     edx, edx; dwFlags
0x1400165f7  mov     rcx, rax; hHeap
0x1400165fa  call    cs:__imp_HeapFree
0x140016600  xor     eax, eax
0x140016602  add     rsp, 48h
0x140016606  pop     r15
0x140016608  pop     r14
0x14001660a  pop     r13
0x14001660c  pop     r12
0x14001660e  pop     rdi
0x14001660f  pop     rsi
0x140016610  pop     rbp
0x140016611  pop     rbx
0x140016612  retn
0x140016613  lea     r14, [rcx+8]
0x140016617  mov     ecx, [rbx+10008h]
0x14001661d  mov     edi, 10000h
0x140016622  sub     edi, ecx
0x140016624  shr     rdi, 1
0x140016627  jz      short loc_140016662
0x140016629  lea     rsi, [r14+rcx]
0x14001662d  mov     r8, rdx; Format
0x140016630  dec     rdi
0x140016633  mov     rcx, rsi; Buffer
0x140016636  mov     rdx, rdi; BufferCount
0x140016639  mov     r9, r13; Args
0x14001663c  call    cs:__imp__vsnwprintf
0x140016642  test    eax, eax
0x140016644  js      short loc_140016654
0x140016646  cdqe
0x140016648  cmp     rax, rdi
0x14001664b  ja      short loc_140016654
0x14001664d  mov     ecx, r12d
0x140016650  jnz     short loc_14001665E
0x140016652  jmp     short loc_140016659
0x140016654  mov     ecx, 8007007Ah
0x140016659  mov     [rsi+rdi*2], r12w
0x14001665e  test    ecx, ecx
0x140016660  jns     short loc_1400166A5
0x140016662  test    bpl, bpl
0x140016665  jnz     short loc_140016600
0x140016667  mov     r8d, [rbx+10008h]; nNumberOfBytesToWrite
0x14001666e  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140016673  mov     rcx, [rbx]; hFile
0x140016676  mov     rdx, r14; lpBuffer
0x140016679  mov     [rsp+88h+lpOverlapped], r12; lpOverlapped
0x14001667e  call    cs:__imp_WriteFile
0x140016684  mov     eax, [rsp+88h+NumberOfBytesWritten]
0x140016688  mov     bpl, 1
0x14001668b  add     [rbx+1000Ch], eax
0x140016691  mov     rdx, [rsp+88h+arg_8]
0x140016699  mov     [rbx+10008h], r12d
0x1400166a0  jmp     loc_140016617
0x1400166a5  mov     ecx, [rbx+10008h]
0x1400166ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400166af  lea     rdx, [rcx+rbx]
0x1400166b3  inc     rax
0x1400166b6  cmp     [rdx+rax*2+8], r12w
0x1400166bc  jnz     short loc_1400166B3
0x1400166be  lea     ecx, [rcx+rax*2]
0x1400166c1  mov     [rbx+10008h], ecx
0x1400166c7  jmp     loc_140016602
```
