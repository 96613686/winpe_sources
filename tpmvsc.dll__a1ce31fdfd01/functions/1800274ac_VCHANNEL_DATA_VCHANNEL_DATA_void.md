# VCHANNEL_DATA::~VCHANNEL_DATA(void)

- ea: `0x1800274ac`
- end: `0x1800274f8`
- name: `??1VCHANNEL_DATA@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(VCHANNEL_DATA *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027e80`

## callees

- `0x18000bf8c`
- `0x1800273d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800274f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall VCHANNEL_DATA::~VCHANNEL_DATA(VCHANNEL_DATA *this)
{
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy((char *)this + 152);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy((char *)this + 128);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy((char *)this + 104);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy((char *)this + 80);
  std::_Tree<std::_Tmap_traits<unsigned char,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>((void **)this + 6);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800274ac  push    rbx
0x1800274ae  sub     rsp, 20h
0x1800274b2  mov     rbx, rcx
0x1800274b5  add     rcx, 98h
0x1800274bc  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800274c1  lea     rcx, [rbx+80h]
0x1800274c8  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800274cd  lea     rcx, [rbx+68h]
0x1800274d1  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800274d6  lea     rcx, [rbx+50h]
0x1800274da  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800274df  lea     rcx, [rbx+30h]
0x1800274e3  call    ??1?$_Tree@V?$_Tmap_traits@EV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<uchar>,std::allocator<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::~_Tree<std::_Tmap_traits<uchar,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<uchar>,std::allocator<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>(void)
0x1800274e8  lea     rcx, [rbx+8]
0x1800274ec  add     rsp, 20h
0x1800274f0  pop     rbx
0x1800274f1  jmp     cs:__imp_DeleteCriticalSection
```
