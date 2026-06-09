# UserWindowPropMangerClassW::CleanupWinpropManager(void)

- ea: `0x18006fec8`
- end: `0x18006ffcd`
- name: `?CleanupWinpropManager@UserWindowPropMangerClassW@@SAXXZ`
- size: `261`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001d168`

## callees

- `0x18006fec8`
- `0x1800700e0`
- `0x180070110`
- `0x1800701a4`
- `0x1800922c8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006ffc6`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006fee7`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006ff1c`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006ff7e`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006fee7`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006ff1c`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006ff7e`

## pseudocode

```c
void UserWindowPropMangerClassW::CleanupWinpropManager(void)
{
  struct UserWindowPropMangerClassW *v0; // r8
  _BYTE v1[16]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v2; // [rsp+30h] [rbp-40h]
  ATOM v3; // [rsp+38h] [rbp-38h]
  __int128 v4; // [rsp+48h] [rbp-28h] BYREF
  __int64 v5; // [rsp+58h] [rbp-18h]

  v0 = UserWindowPropMangerClassW::s_instance;
  if ( *((_BYTE *)UserWindowPropMangerClassW::s_instance + 32) )
  {
    GlobalDeleteAtom(*(_WORD *)UserWindowPropMangerClassW::s_instance);
    HashTable<bool>::begin((char *)UserWindowPropMangerClassW::s_instance + 16, v1);
    v5 = 0;
    v4 = 0;
    while ( v2 )
    {
      GlobalDeleteAtom(v3);
      HashTable<bool>::HashTableIter::operator++(v1);
    }
    HashTable<void *>::HashTableIter::~HashTableIter(&v4);
    HashTable<void *>::HashTableIter::~HashTableIter(v1);
    HashTable<bool>::Cleanup((char *)UserWindowPropMangerClassW::s_instance + 16);
    HashTable<bool>::begin((char *)UserWindowPropMangerClassW::s_instance + 24, v1);
    v5 = 0;
    v4 = 0;
    while ( v2 )
    {
      GlobalDeleteAtom(v3);
      HashTable<bool>::HashTableIter::operator++(v1);
    }
    HashTable<void *>::HashTableIter::~HashTableIter(&v4);
    HashTable<void *>::HashTableIter::~HashTableIter(v1);
    HashTable<bool>::Cleanup((char *)UserWindowPropMangerClassW::s_instance + 24);
    v0 = UserWindowPropMangerClassW::s_instance;
  }
  RtlFreeHeap(pUserHeap, 0, v0);
}

```

## disassembly

```asm
0x18006fec8  push    rbp
0x18006feca  mov     rbp, rsp
0x18006fecd  sub     rsp, 70h
0x18006fed1  mov     r8, cs:?s_instance@UserWindowPropMangerClassW@@0PEAV1@EA; UserWindowPropMangerClassW * UserWindowPropMangerClassW::s_instance
0x18006fed8  cmp     byte ptr [r8+20h], 0
0x18006fedd  jz      loc_18006FFB8
0x18006fee3  movzx   ecx, word ptr [r8]; nAtom
0x18006fee7  call    cs:__imp_GlobalDeleteAtom
0x18006feed  mov     rcx, cs:?s_instance@UserWindowPropMangerClassW@@0PEAV1@EA; UserWindowPropMangerClassW * UserWindowPropMangerClassW::s_instance
0x18006fef4  lea     rdx, [rbp+var_50]
0x18006fef8  add     rcx, 10h
0x18006fefc  call    ?begin@?$HashTable@_N@@QEAA?AUHashTableIter@1@XZ; HashTable<bool>::begin(void)
0x18006ff01  xorps   xmm0, xmm0
0x18006ff04  mov     [rbp+var_18], 0
0x18006ff0c  movdqu  [rbp+var_28], xmm0
0x18006ff11  cmp     [rbp+var_40], 0
0x18006ff16  jz      short loc_18006FF2D
0x18006ff18  movzx   ecx, [rbp+var_38]; nAtom
0x18006ff1c  call    cs:__imp_GlobalDeleteAtom
0x18006ff22  lea     rcx, [rbp+var_50]
0x18006ff26  call    ??EHashTableIter@?$HashTable@_N@@QEAAAEAU01@XZ; HashTable<bool>::HashTableIter::operator++(void)
0x18006ff2b  jmp     short loc_18006FF11
0x18006ff2d  lea     rcx, [rbp+var_28]
0x18006ff31  call    ??1HashTableIter@?$HashTable@PEAX@@QEAA@XZ; HashTable<void *>::HashTableIter::~HashTableIter(void)
0x18006ff36  lea     rcx, [rbp+var_50]
0x18006ff3a  call    ??1HashTableIter@?$HashTable@PEAX@@QEAA@XZ; HashTable<void *>::HashTableIter::~HashTableIter(void)
0x18006ff3f  mov     rcx, cs:?s_instance@UserWindowPropMangerClassW@@0PEAV1@EA; UserWindowPropMangerClassW * UserWindowPropMangerClassW::s_instance
0x18006ff46  add     rcx, 10h
0x18006ff4a  call    ?Cleanup@?$HashTable@_N@@QEAAXXZ; HashTable<bool>::Cleanup(void)
0x18006ff4f  mov     rcx, cs:?s_instance@UserWindowPropMangerClassW@@0PEAV1@EA; UserWindowPropMangerClassW * UserWindowPropMangerClassW::s_instance
0x18006ff56  lea     rdx, [rbp+var_50]
0x18006ff5a  add     rcx, 18h
0x18006ff5e  call    ?begin@?$HashTable@_N@@QEAA?AUHashTableIter@1@XZ; HashTable<bool>::begin(void)
0x18006ff63  xorps   xmm0, xmm0
0x18006ff66  mov     [rbp+var_18], 0
0x18006ff6e  movdqu  [rbp+var_28], xmm0
0x18006ff73  cmp     [rbp+var_40], 0
0x18006ff78  jz      short loc_18006FF8F
0x18006ff7a  movzx   ecx, [rbp+var_38]; nAtom
0x18006ff7e  call    cs:__imp_GlobalDeleteAtom
0x18006ff84  lea     rcx, [rbp+var_50]
0x18006ff88  call    ??EHashTableIter@?$HashTable@_N@@QEAAAEAU01@XZ; HashTable<bool>::HashTableIter::operator++(void)
0x18006ff8d  jmp     short loc_18006FF73
0x18006ff8f  lea     rcx, [rbp+var_28]
0x18006ff93  call    ??1HashTableIter@?$HashTable@PEAX@@QEAA@XZ; HashTable<void *>::HashTableIter::~HashTableIter(void)
0x18006ff98  lea     rcx, [rbp+var_50]
0x18006ff9c  call    ??1HashTableIter@?$HashTable@PEAX@@QEAA@XZ; HashTable<void *>::HashTableIter::~HashTableIter(void)
0x18006ffa1  mov     rcx, cs:?s_instance@UserWindowPropMangerClassW@@0PEAV1@EA; UserWindowPropMangerClassW * UserWindowPropMangerClassW::s_instance
0x18006ffa8  add     rcx, 18h
0x18006ffac  call    ?Cleanup@?$HashTable@_N@@QEAAXXZ; HashTable<bool>::Cleanup(void)
0x18006ffb1  mov     r8, cs:?s_instance@UserWindowPropMangerClassW@@0PEAV1@EA; UserWindowPropMangerClassW * UserWindowPropMangerClassW::s_instance
0x18006ffb8  mov     rcx, cs:pUserHeap
0x18006ffbf  xor     edx, edx
0x18006ffc1  add     rsp, 70h
0x18006ffc5  pop     rbp
0x18006ffc6  jmp     cs:__imp_RtlFreeHeap
```
