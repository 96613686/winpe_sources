# CVisualStyleDataManager::DeleteEntriesWithZeroReferenceCount(void)

- ea: `0x180005754`
- end: `0x18000579c`
- name: `?DeleteEntriesWithZeroReferenceCount@CVisualStyleDataManager@@AEAAXXZ`
- size: `72`
- prototype: `void __fastcall(CVisualStyleDataManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000546c`

## callees

- `0x180005754`
- `0x1800057a4`

## pseudocode

```c
void __fastcall CVisualStyleDataManager::DeleteEntriesWithZeroReferenceCount(CVisualStyleDataManager *this)
{
  int v1; // edx
  int v2; // ebx
  CVisualStyleDataManager *v3; // rcx

  v1 = dword_1800171E8;
  v2 = 0;
  while ( v2 < v1 )
  {
    v3 = (CVisualStyleDataManager *)(1600LL * v2);
    if ( *(int *)((char *)v3 + CThemeManagerAPIRequest::s_visualStyleDataManager + 1592) > 0 )
    {
      ++v2;
    }
    else
    {
      CVisualStyleDataManager::DeleteEntry(v3, v2);
      v1 = dword_1800171E8;
    }
  }
}

```

## disassembly

```asm
0x180005754  push    rbx
0x180005756  sub     rsp, 20h
0x18000575a  mov     edx, cs:dword_1800171E8
0x180005760  xor     ebx, ebx
0x180005762  test    edx, edx
0x180005764  jle     short loc_180005796
0x180005766  movsxd  rax, ebx
0x180005769  imul    rcx, rax, 640h; this
0x180005770  mov     rax, cs:?s_visualStyleDataManager@CThemeManagerAPIRequest@@0VCVisualStyleDataManager@@A; CVisualStyleDataManager CThemeManagerAPIRequest::s_visualStyleDataManager
0x180005777  cmp     dword ptr [rcx+rax+638h], 0
0x18000577f  jg      short loc_180005790
0x180005781  mov     edx, ebx; int
0x180005783  call    ?DeleteEntry@CVisualStyleDataManager@@AEAAXH@Z; CVisualStyleDataManager::DeleteEntry(int)
0x180005788  mov     edx, cs:dword_1800171E8
0x18000578e  jmp     short loc_180005792
0x180005790  inc     ebx
0x180005792  cmp     ebx, edx
0x180005794  jl      short loc_180005766
0x180005796  add     rsp, 20h
0x18000579a  pop     rbx
0x18000579b  retn
```
