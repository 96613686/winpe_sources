# UserWindowPropMangerClassA::CleanupWinpropManager(void)

- ea: `0x18006ffd4`
- end: `0x1800700d9`
- name: `?CleanupWinpropManager@UserWindowPropMangerClassA@@SAXXZ`
- size: `261`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001d168`

## callees

- `0x18006ffd4`
- `0x1800700e0`
- `0x180070110`
- `0x1800701a4`
- `0x1800922c8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800700d2`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006fff3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180070028`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007008a`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006fff3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180070028`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007008a`

## pseudocode

```c
void UserWindowPropMangerClassA::CleanupWinpropManager(void)
{
  struct UserWindowPropMangerClassA *v0; // r8
  _BYTE v1[16]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v2; // [rsp+30h] [rbp-40h]
  ATOM v3; // [rsp+38h] [rbp-38h]
  __int128 v4; // [rsp+48h] [rbp-28h] BYREF
  __int64 v5; // [rsp+58h] [rbp-18h]

  v0 = UserWindowPropMangerClassA::s_instance;
  if ( *((_BYTE *)UserWindowPropMangerClassA::s_instance + 32) )
  {
    GlobalDeleteAtom(*(_WORD *)UserWindowPropMangerClassA::s_instance);
    HashTable<bool>::begin((char *)UserWindowPropMangerClassA::s_instance + 16, v1);
    v5 = 0;
    v4 = 0;
    while ( v2 )
    {
      GlobalDeleteAtom(v3);
      HashTable<bool>::HashTableIter::operator++(v1);
    }
    HashTable<void *>::HashTableIter::~HashTableIter(&v4);
    HashTable<void *>::HashTableIter::~HashTableIter(v1);
    HashTable<bool>::Cleanup((char *)UserWindowPropMangerClassA::s_instance + 16);
    HashTable<bool>::begin((char *)UserWindowPropMangerClassA::s_instance + 24, v1);
    v5 = 0;
    v4 = 0;
    while ( v2 )
    {
      GlobalDeleteAtom(v3);
      HashTable<bool>::HashTableIter::operator++(v1);
    }
    HashTable<void *>::HashTableIter::~HashTableIter(&v4);
    HashTable<void *>::HashTableIter::~HashTableIter(v1);
    HashTable<bool>::Cleanup((char *)UserWindowPropMangerClassA::s_instance + 24);
    v0 = UserWindowPropMangerClassA::s_instance;
  }
  RtlFreeHeap(pUserHeap, 0, v0);
}

```

## disassembly

```asm
0x18006ffd4  push    rbp
0x18006ffd6  mov     rbp, rsp
0x18006ffd9  sub     rsp, 70h
0x18006ffdd  mov     r8, cs:?s_instance@UserWindowPropMangerClassA@@0PEAV1@EA; UserWindowPropMangerClassA * UserWindowPropMangerClassA::s_instance
0x18006ffe4  cmp     byte ptr [r8+20h], 0
0x18006ffe9  jz      loc_1800700C4
0x18006ffef  movzx   ecx, word ptr [r8]; nAtom
0x18006fff3  call    cs:__imp_GlobalDeleteAtom
0x18006fff9  mov     rcx, cs:?s_instance@UserWindowPropMangerClassA@@0PEAV1@EA; UserWindowPropMangerClassA * UserWindowPropMangerClassA::s_instance
0x180070000  lea     rdx, [rbp+var_50]
0x180070004  add     rcx, 10h
0x180070008  call    ?begin@?$HashTable@_N@@QEAA?AUHashTableIter@1@XZ; HashTable<bool>::begin(void)
0x18007000d  xorps   xmm0, xmm0
0x180070010  mov     [rbp+var_18], 0
0x180070018  movdqu  [rbp+var_28], xmm0
0x18007001d  cmp     [rbp+var_40], 0
0x180070022  jz      short loc_180070039
0x180070024  movzx   ecx, [rbp+var_38]; nAtom
0x180070028  call    cs:__imp_GlobalDeleteAtom
0x18007002e  lea     rcx, [rbp+var_50]
0x180070032  call    ??EHashTableIter@?$HashTable@_N@@QEAAAEAU01@XZ; HashTable<bool>::HashTableIter::operator++(void)
0x180070037  jmp     short loc_18007001D
0x180070039  lea     rcx, [rbp+var_28]
0x18007003d  call    ??1HashTableIter@?$HashTable@PEAX@@QEAA@XZ; HashTable<void *>::HashTableIter::~HashTableIter(void)
0x180070042  lea     rcx, [rbp+var_50]
0x180070046  call    ??1HashTableIter@?$HashTable@PEAX@@QEAA@XZ; HashTable<void *>::HashTableIter::~HashTableIter(void)
0x18007004b  mov     rcx, cs:?s_instance@UserWindowPropMangerClassA@@0PEAV1@EA; UserWindowPropMangerClassA * UserWindowPropMangerClassA::s_instance
0x180070052  add     rcx, 10h
0x180070056  call    ?Cleanup@?$HashTable@_N@@QEAAXXZ; HashTable<bool>::Cleanup(void)
0x18007005b  mov     rcx, cs:?s_instance@UserWindowPropMangerClassA@@0PEAV1@EA; UserWindowPropMangerClassA * UserWindowPropMangerClassA::s_instance
0x180070062  lea     rdx, [rbp+var_50]
0x180070066  add     rcx, 18h
0x18007006a  call    ?begin@?$HashTable@_N@@QEAA?AUHashTableIter@1@XZ; HashTable<bool>::begin(void)
0x18007006f  xorps   xmm0, xmm0
0x180070072  mov     [rbp+var_18], 0
0x18007007a  movdqu  [rbp+var_28], xmm0
0x18007007f  cmp     [rbp+var_40], 0
0x180070084  jz      short loc_18007009B
0x180070086  movzx   ecx, [rbp+var_38]; nAtom
0x18007008a  call    cs:__imp_GlobalDeleteAtom
0x180070090  lea     rcx, [rbp+var_50]
0x180070094  call    ??EHashTableIter@?$HashTable@_N@@QEAAAEAU01@XZ; HashTable<bool>::HashTableIter::operator++(void)
0x180070099  jmp     short loc_18007007F
0x18007009b  lea     rcx, [rbp+var_28]
0x18007009f  call    ??1HashTableIter@?$HashTable@PEAX@@QEAA@XZ; HashTable<void *>::HashTableIter::~HashTableIter(void)
0x1800700a4  lea     rcx, [rbp+var_50]
0x1800700a8  call    ??1HashTableIter@?$HashTable@PEAX@@QEAA@XZ; HashTable<void *>::HashTableIter::~HashTableIter(void)
0x1800700ad  mov     rcx, cs:?s_instance@UserWindowPropMangerClassA@@0PEAV1@EA; UserWindowPropMangerClassA * UserWindowPropMangerClassA::s_instance
0x1800700b4  add     rcx, 18h
0x1800700b8  call    ?Cleanup@?$HashTable@_N@@QEAAXXZ; HashTable<bool>::Cleanup(void)
0x1800700bd  mov     r8, cs:?s_instance@UserWindowPropMangerClassA@@0PEAV1@EA; UserWindowPropMangerClassA * UserWindowPropMangerClassA::s_instance
0x1800700c4  mov     rcx, cs:pUserHeap
0x1800700cb  xor     edx, edx
0x1800700cd  add     rsp, 70h
0x1800700d1  pop     rbp
0x1800700d2  jmp     cs:__imp_RtlFreeHeap
```
