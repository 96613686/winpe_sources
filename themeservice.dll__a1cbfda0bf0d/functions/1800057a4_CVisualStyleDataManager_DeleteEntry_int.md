# CVisualStyleDataManager::DeleteEntry(int)

- ea: `0x1800057a4`
- end: `0x180005845`
- name: `?DeleteEntry@CVisualStyleDataManager@@AEAAXH@Z`
- size: `161`
- prototype: `void __fastcall(CVisualStyleDataManager *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f74`
- `0x180005754`

## callees

- `0x1800057a4`
- `0x18000f9c2`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057e9`

## pseudocode

```c
void __fastcall CVisualStyleDataManager::DeleteEntry(CVisualStyleDataManager *this, int a2)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  void *v4; // rcx
  void *v5; // rcx
  _BYTE Src[1608]; // [rsp+20h] [rbp-648h] BYREF

  v2 = CThemeManagerAPIRequest::s_visualStyleDataManager;
  v3 = 1600LL * a2;
  v4 = *(void **)(v3 + CThemeManagerAPIRequest::s_visualStyleDataManager + 1584);
  if ( v4 )
  {
    CloseHandle(v4);
    v2 = CThemeManagerAPIRequest::s_visualStyleDataManager;
  }
  v5 = *(void **)(v3 + v2 + 1576);
  if ( v5 )
  {
    CloseHandle(v5);
    v2 = CThemeManagerAPIRequest::s_visualStyleDataManager;
  }
  memcpy_0(Src, (const void *)(v2 + 1600LL * --dword_1800171E8), 0x640u);
  memcpy_0((void *)(v3 + v2), Src, 0x640u);
}

```

## disassembly

```asm
0x1800057a4  mov     [rsp+arg_0], rbx
0x1800057a9  push    rdi
0x1800057aa  sub     rsp, 660h
0x1800057b1  mov     rbx, cs:?s_visualStyleDataManager@CThemeManagerAPIRequest@@0VCVisualStyleDataManager@@A; CVisualStyleDataManager CThemeManagerAPIRequest::s_visualStyleDataManager
0x1800057b8  movsxd  rax, edx
0x1800057bb  imul    rdi, rax, 640h
0x1800057c2  mov     rcx, [rdi+rbx+630h]; hObject
0x1800057ca  test    rcx, rcx
0x1800057cd  jz      short loc_1800057DC
0x1800057cf  call    cs:__imp_CloseHandle
0x1800057d5  mov     rbx, cs:?s_visualStyleDataManager@CThemeManagerAPIRequest@@0VCVisualStyleDataManager@@A; CVisualStyleDataManager CThemeManagerAPIRequest::s_visualStyleDataManager
0x1800057dc  mov     rcx, [rdi+rbx+628h]; hObject
0x1800057e4  test    rcx, rcx
0x1800057e7  jz      short loc_1800057F6
0x1800057e9  call    cs:__imp_CloseHandle
0x1800057ef  mov     rbx, cs:?s_visualStyleDataManager@CThemeManagerAPIRequest@@0VCVisualStyleDataManager@@A; CVisualStyleDataManager CThemeManagerAPIRequest::s_visualStyleDataManager
0x1800057f6  mov     eax, cs:dword_1800171E8
0x1800057fc  lea     rcx, [rsp+668h+Src]; void *
0x180005801  dec     eax
0x180005803  mov     r8d, 640h; Size
0x180005809  mov     cs:dword_1800171E8, eax
0x18000580f  cdqe
0x180005811  imul    rdx, rax, 640h
0x180005818  add     rdx, rbx; Src
0x18000581b  call    memcpy_0
0x180005820  lea     rcx, [rdi+rbx]; void *
0x180005824  mov     r8d, 640h; Size
0x18000582a  lea     rdx, [rsp+668h+Src]; Src
0x18000582f  call    memcpy_0
0x180005834  mov     rbx, [rsp+668h+arg_0]
0x18000583c  add     rsp, 660h
0x180005843  pop     rdi
0x180005844  retn
```
