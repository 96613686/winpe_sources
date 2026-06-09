# CredentialManager::~CredentialManager(void)

- ea: `0x18001549c`
- end: `0x1800154c5`
- name: `??1CredentialManager@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CredentialManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022890`

## callees

- `0x180015430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800154a9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800154a9`

## pseudocode

```c
void __fastcall CredentialManager::~CredentialManager(CredentialManager *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)this + 16);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(this);
}

```

## disassembly

```asm
0x18001549c  push    rbx
0x18001549e  sub     rsp, 20h
0x1800154a2  mov     rbx, rcx
0x1800154a5  add     rcx, 20h ; ' '; lpCriticalSection
0x1800154a9  call    cs:__imp_DeleteCriticalSection
0x1800154af  lea     rcx, [rbx+10h]
0x1800154b3  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@Uwstring_iless@CredentialManager@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800154b8  mov     rcx, rbx
0x1800154bb  add     rsp, 20h
0x1800154bf  pop     rbx
0x1800154c0  jmp     ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@Uwstring_iless@CredentialManager@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
```
