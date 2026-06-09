# SOS_ResourceManager::AutoSwitchResourceGroup::~AutoSwitchResourceGroup(void)

- ea: `0x10041fa30`
- end: `0x10041faa5`
- name: `??1AutoSwitchResourceGroup@SOS_ResourceManager@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(SOS_ResourceManager::AutoSwitchResourceGroup *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10041ef70`
- `0x100454960`

## callees

- `0x10040af70`
- `0x10041fa30`

## import_xrefs

- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x10041fa92`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x10041fa51`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x10041fa51`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x10041fa4a`

## pseudocode

```c
void __fastcall SOS_ResourceManager::AutoSwitchResourceGroup::~AutoSwitchResourceGroup(
        SOS_ResourceManager::AutoSwitchResourceGroup *this)
{
  struct SOS_ResourceGroup *v2; // rdx
  __int64 v3; // rbx

  if ( *(_QWORD *)this )
  {
    v2 = (struct SOS_ResourceGroup *)*((_QWORD *)this + 1);
    if ( v2 != *(struct SOS_ResourceGroup **)this )
    {
      SOS_ResourceManager::BindCurrentTaskToGroup(SOS_PublicGlobals::sm_ResourceManager, v2);
      v3 = *((_QWORD *)this + 1);
      if ( *(_DWORD *)(v3 + 164) >= 3u )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v3 + 64));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 40), 0xFFFFFFFF) == 1 )
        {
          if ( *(_QWORD *)(v3 + 24) )
            TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v3 + 32), (_QWORD *)v3);
          SOS_ResourceGroup::Destroy((SOS_ResourceGroup *)v3);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x10041fa30  push    rbx
0x10041fa32  sub     rsp, 20h
0x10041fa36  mov     rax, [rcx]
0x10041fa39  mov     rbx, rcx
0x10041fa3c  test    rax, rax
0x10041fa3f  jz      short loc_10041FA9F
0x10041fa41  mov     rdx, [rcx+8]
0x10041fa45  cmp     rdx, rax
0x10041fa48  jz      short loc_10041FA9F
0x10041fa4a  mov     rcx, cs:__imp_?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x10041fa51  call    cs:__imp_?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z; SOS_ResourceManager::BindCurrentTaskToGroup(SOS_ResourceGroup *)
0x10041fa57  mov     rbx, [rbx+8]
0x10041fa5b  cmp     dword ptr [rbx+0A4h], 3
0x10041fa62  jb      short loc_10041FA9F
0x10041fa64  lock dec dword ptr [rbx+40h]
0x10041fa68  mov     eax, 0FFFFFFFFh
0x10041fa6d  lock xadd [rbx+28h], eax
0x10041fa72  cmp     eax, 1
0x10041fa75  jnz     short loc_10041FA9F
0x10041fa77  cmp     qword ptr [rbx+18h], 0
0x10041fa7c  jz      short loc_10041FA8A
0x10041fa7e  mov     rcx, [rbx+20h]
0x10041fa82  mov     rdx, rbx
0x10041fa85  call    ?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)
0x10041fa8a  mov     rcx, rbx
0x10041fa8d  add     rsp, 20h
0x10041fa91  pop     rbx
0x10041fa92  jmp     cs:__imp_?Destroy@SOS_ResourceGroup@@QEAAXXZ; SOS_ResourceGroup::Destroy(void)
0x10041fa9f  add     rsp, 20h
0x10041faa3  pop     rbx
0x10041faa4  retn
```
