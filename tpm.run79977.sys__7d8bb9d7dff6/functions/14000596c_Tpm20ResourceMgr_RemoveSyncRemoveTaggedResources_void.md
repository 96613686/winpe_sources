# Tpm20ResourceMgr::RemoveSyncRemoveTaggedResources(void)

- ea: `0x14000596c`
- end: `0x1400059f4`
- name: `?RemoveSyncRemoveTaggedResources@Tpm20ResourceMgr@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(Tpm20ResourceMgr *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140006fac`

## callees

- `0x14000596c`
- `0x1400078b8`
- `0x1400078e8`
- `0x140008fec`

## pseudocode

```c
void __fastcall Tpm20ResourceMgr::RemoveSyncRemoveTaggedResources(Tpm20ResourceMgr *this)
{
  char *v1; // rax
  char *v2; // rsi
  char *v3; // rdi
  struct Tpm20Resource *v4; // rbx
  Tpm20ResourceMgr *v5; // rcx

  v1 = (char *)*((_QWORD *)this + 2);
  v2 = (char *)this + 8;
  if ( v1 != (char *)this + 8 )
  {
    do
    {
      v3 = (char *)*((_QWORD *)v1 + 1);
      v4 = (struct Tpm20Resource *)(v1 - 16);
      if ( v1[45] )
      {
        v5 = (Tpm20ResourceMgr *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids);
        if ( *((_BYTE *)v4 + 60) )
          Tpm20ResourceMgr::RemovedLoadedResource(v5, 0, v4);
        else
          Tpm20ResourceMgr::RemovedNonloadedResource(v5, 0, v4);
      }
      v1 = v3;
    }
    while ( v3 != v2 );
  }
}

```

## disassembly

```asm
0x14000596c  mov     [rsp+arg_0], rbx
0x140005971  mov     [rsp+arg_8], rsi
0x140005976  push    rdi
0x140005977  sub     rsp, 20h
0x14000597b  mov     rax, [rcx+10h]
0x14000597f  lea     rsi, [rcx+8]
0x140005983  cmp     rax, rsi
0x140005986  jz      short loc_1400059E3
0x140005988  mov     rdi, [rax+8]
0x14000598c  lea     rbx, [rax-10h]
0x140005990  cmp     byte ptr [rbx+3Dh], 0
0x140005994  jz      short loc_1400059DB
0x140005996  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000599d  lea     rax, WPP_GLOBAL_Control
0x1400059a4  cmp     rcx, rax
0x1400059a7  jz      short loc_1400059C5
0x1400059a9  mov     eax, [rcx+2Ch]
0x1400059ac  test    al, 4
0x1400059ae  jz      short loc_1400059C5
0x1400059b0  mov     rcx, [rcx+18h]
0x1400059b4  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x1400059bb  mov     edx, 2Eh ; '.'
0x1400059c0  call    WPP_SF_
0x1400059c5  xor     edx, edx; struct Tpm20Context *
0x1400059c7  mov     r8, rbx; struct Tpm20Resource *
0x1400059ca  cmp     [rbx+3Ch], dl
0x1400059cd  jz      short loc_1400059D6
0x1400059cf  call    ?RemovedLoadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z; Tpm20ResourceMgr::RemovedLoadedResource(Tpm20Context const *,Tpm20Resource *)
0x1400059d4  jmp     short loc_1400059DB
0x1400059d6  call    ?RemovedNonloadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z; Tpm20ResourceMgr::RemovedNonloadedResource(Tpm20Context const *,Tpm20Resource *)
0x1400059db  mov     rax, rdi
0x1400059de  cmp     rdi, rsi
0x1400059e1  jnz     short loc_140005988
0x1400059e3  mov     rbx, [rsp+28h+arg_0]
0x1400059e8  mov     rsi, [rsp+28h+arg_8]
0x1400059ed  add     rsp, 20h
0x1400059f1  pop     rdi
0x1400059f2  retn
```
