# CElevatedFactoryServerManager::~CElevatedFactoryServerManager(void)

- ea: `0x180001b6c`
- end: `0x180001ba6`
- name: `??1CElevatedFactoryServerManager@@MEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CElevatedFactoryServerManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c40`

## callees

- `0x180001b6c`
- `0x180003400`

## pseudocode

```c
void __fastcall CElevatedFactoryServerManager::~CElevatedFactoryServerManager(CElevatedFactoryServerManager *this)
{
  struct _DPA *v2; // rcx

  *(_QWORD *)this = &CElevatedFactoryServerManager::`vftable';
  v2 = (struct _DPA *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    g_pfn_DPA_DestroyCallback(v2, (PFNDAENUMCALLBACK)DPA_DeleteCB<CElevatedFactoryServerManager::CFactoryData>, 0);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180001b6c  push    rbx
0x180001b6e  sub     rsp, 20h
0x180001b72  lea     rax, ??_7CElevatedFactoryServerManager@@6B@; const CElevatedFactoryServerManager::`vftable'
0x180001b79  mov     rbx, rcx
0x180001b7c  mov     [rcx], rax
0x180001b7f  mov     rcx, [rcx+8]; hdpa
0x180001b83  test    rcx, rcx
0x180001b86  jz      short loc_180001BA0
0x180001b88  xor     r8d, r8d; pData
0x180001b8b  lea     rdx, ??$DPA_DeleteCB@VCFactoryData@CElevatedFactoryServerManager@@@@YAHPEAVCFactoryData@CElevatedFactoryServerManager@@PEAX@Z; pfnCB
0x180001b92  call    cs:g_pfn_DPA_DestroyCallback
0x180001b98  mov     qword ptr [rbx+8], 0
0x180001ba0  add     rsp, 20h
0x180001ba4  pop     rbx
0x180001ba5  retn
```
