# CVolume::MarkSelfForDelete(void)

- ea: `0x180001448`
- end: `0x18000148c`
- name: `?MarkSelfForDelete@CVolume@@AEAAXXZ`
- size: `68`
- prototype: `void __fastcall(CVolume *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180002488`
- `0x18000756c`

## callees

- `0x180001448`
- `0x180001494`
- `0x180001500`
- `0x180001588`

## pseudocode

```c
void __fastcall CVolume::MarkSelfForDelete(CVolume *this)
{
  int v1; // eax

  v1 = *((_DWORD *)this + 4);
  if ( (v1 & 0x20) == 0 )
  {
    *((_DWORD *)this + 4) = v1 | 0x20;
    CObjIdIndexChangeNotifier::UnInitialize((CVolume *)((char *)this + 576));
    CLogFile::UnInitialize((CVolume *)((char *)this + 312));
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    CVolumeManager::RemoveVolumeFromLinkedList(*((CVolumeManager **)this + 5), this);
  }
}

```

## disassembly

```asm
0x180001448  push    rbx
0x18000144a  sub     rsp, 20h
0x18000144e  mov     eax, [rcx+10h]
0x180001451  mov     rbx, rcx
0x180001454  test    al, 20h
0x180001456  jnz     short loc_180001486
0x180001458  or      eax, 20h
0x18000145b  mov     [rcx+10h], eax
0x18000145e  add     rcx, 240h; this
0x180001465  call    ?UnInitialize@CObjIdIndexChangeNotifier@@QEAAXXZ; CObjIdIndexChangeNotifier::UnInitialize(void)
0x18000146a  lea     rcx, [rbx+138h]; this
0x180001471  call    ?UnInitialize@CLogFile@@QEAAXXZ; CLogFile::UnInitialize(void)
0x180001476  lock inc dword ptr [rbx+8]
0x18000147a  mov     rcx, [rbx+28h]; this
0x18000147e  mov     rdx, rbx; struct CVolume *
0x180001481  call    ?RemoveVolumeFromLinkedList@CVolumeManager@@QEAAXPEBVCVolume@@@Z; CVolumeManager::RemoveVolumeFromLinkedList(CVolume const *)
0x180001486  add     rsp, 20h
0x18000148a  pop     rbx
0x18000148b  retn
```
