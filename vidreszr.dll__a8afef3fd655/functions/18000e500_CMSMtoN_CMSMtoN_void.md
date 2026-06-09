# CMSMtoN::~CMSMtoN(void)

- ea: `0x18000e500`
- end: `0x18000e680`
- name: `??1CMSMtoN@@QEAA@XZ`
- size: `384`
- prototype: `void __fastcall(CMSMtoN *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011830`
- `0x180011ab0`

## callees

- `0x180001968`
- `0x18000e500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e584`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e593`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e623`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e632`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e584`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e593`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e623`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e632`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e56b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e575`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e60a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e614`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e56b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e575`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e60a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e614`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e59d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e63c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e646`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e650`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e65a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e664`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e59d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e63c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e646`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e650`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e65a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e664`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e673`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000e54f`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000e561`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000e5ee`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000e600`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000e54f`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000e561`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000e5ee`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000e600`

## pseudocode

```c
void __fastcall CMSMtoN::~CMSMtoN(CMSMtoN *this, unsigned __int64 a2)
{
  void *v3; // rcx
  bool v4; // cf
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  *(_QWORD *)this = &CMSMtoN::`vftable';
  v3 = (void *)*((_QWORD *)this + 95);
  if ( v3 )
  {
    operator delete(v3, a2);
    *((_QWORD *)this + 95) = 0;
  }
  v4 = *((_DWORD *)this + 176) < 2u;
  *((_DWORD *)this + 30) = 1;
  if ( !v4 )
  {
    v5 = (void *)*((_QWORD *)this + 82);
    if ( v5 )
      AvRevertMmThreadCharacteristics(v5);
    v6 = (void *)*((_QWORD *)this + 83);
    if ( v6 )
      AvRevertMmThreadCharacteristics(v6);
    SetEvent(*((HANDLE *)this + 1));
    SetEvent(*((HANDLE *)this + 3));
    WaitForSingleObject(*((HANDLE *)this + 9), 0xFFFFFFFF);
    WaitForSingleObject(*((HANDLE *)this + 10), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 9));
    CloseHandle(*((HANDLE *)this + 1));
    CloseHandle(*((HANDLE *)this + 2));
    CloseHandle(*((HANDLE *)this + 10));
    CloseHandle(*((HANDLE *)this + 3));
    CloseHandle(*((HANDLE *)this + 4));
    if ( *((_DWORD *)this + 176) == 4 )
    {
      v7 = (void *)*((_QWORD *)this + 84);
      if ( v7 )
        AvRevertMmThreadCharacteristics(v7);
      v8 = (void *)*((_QWORD *)this + 85);
      if ( v8 )
        AvRevertMmThreadCharacteristics(v8);
      SetEvent(*((HANDLE *)this + 5));
      SetEvent(*((HANDLE *)this + 7));
      WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF);
      WaitForSingleObject(*((HANDLE *)this + 12), 0xFFFFFFFF);
      CloseHandle(*((HANDLE *)this + 11));
      CloseHandle(*((HANDLE *)this + 5));
      CloseHandle(*((HANDLE *)this + 6));
      CloseHandle(*((HANDLE *)this + 12));
      CloseHandle(*((HANDLE *)this + 7));
      CloseHandle(*((HANDLE *)this + 8));
    }
  }
}

```

## disassembly

```asm
0x18000e500  push    rbx
0x18000e502  sub     rsp, 20h
0x18000e506  lea     rax, ??_7CMSMtoN@@6B@; const CMSMtoN::`vftable'
0x18000e50d  mov     rbx, rcx
0x18000e510  mov     [rcx], rax
0x18000e513  mov     rcx, [rcx+2F8h]; void *
0x18000e51a  test    rcx, rcx
0x18000e51d  jz      short loc_18000E52F
0x18000e51f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e524  mov     qword ptr [rbx+2F8h], 0
0x18000e52f  cmp     dword ptr [rbx+2C0h], 2
0x18000e536  mov     dword ptr [rbx+78h], 1
0x18000e53d  jb      loc_18000E67A
0x18000e543  mov     rcx, [rbx+290h]; AvrtHandle
0x18000e54a  test    rcx, rcx
0x18000e54d  jz      short loc_18000E555
0x18000e54f  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000e555  mov     rcx, [rbx+298h]; AvrtHandle
0x18000e55c  test    rcx, rcx
0x18000e55f  jz      short loc_18000E567
0x18000e561  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000e567  mov     rcx, [rbx+8]; hEvent
0x18000e56b  call    cs:__imp_SetEvent
0x18000e571  mov     rcx, [rbx+18h]; hEvent
0x18000e575  call    cs:__imp_SetEvent
0x18000e57b  mov     rcx, [rbx+48h]; hHandle
0x18000e57f  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000e584  call    cs:__imp_WaitForSingleObject
0x18000e58a  mov     rcx, [rbx+50h]; hHandle
0x18000e58e  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000e593  call    cs:__imp_WaitForSingleObject
0x18000e599  mov     rcx, [rbx+48h]; hObject
0x18000e59d  call    cs:__imp_CloseHandle
0x18000e5a3  mov     rcx, [rbx+8]; hObject
0x18000e5a7  call    cs:__imp_CloseHandle
0x18000e5ad  mov     rcx, [rbx+10h]; hObject
0x18000e5b1  call    cs:__imp_CloseHandle
0x18000e5b7  mov     rcx, [rbx+50h]; hObject
0x18000e5bb  call    cs:__imp_CloseHandle
0x18000e5c1  mov     rcx, [rbx+18h]; hObject
0x18000e5c5  call    cs:__imp_CloseHandle
0x18000e5cb  mov     rcx, [rbx+20h]; hObject
0x18000e5cf  call    cs:__imp_CloseHandle
0x18000e5d5  cmp     dword ptr [rbx+2C0h], 4
0x18000e5dc  jnz     loc_18000E67A
0x18000e5e2  mov     rcx, [rbx+2A0h]; AvrtHandle
0x18000e5e9  test    rcx, rcx
0x18000e5ec  jz      short loc_18000E5F4
0x18000e5ee  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000e5f4  mov     rcx, [rbx+2A8h]; AvrtHandle
0x18000e5fb  test    rcx, rcx
0x18000e5fe  jz      short loc_18000E606
0x18000e600  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000e606  mov     rcx, [rbx+28h]; hEvent
0x18000e60a  call    cs:__imp_SetEvent
0x18000e610  mov     rcx, [rbx+38h]; hEvent
0x18000e614  call    cs:__imp_SetEvent
0x18000e61a  mov     rcx, [rbx+58h]; hHandle
0x18000e61e  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000e623  call    cs:__imp_WaitForSingleObject
0x18000e629  mov     rcx, [rbx+60h]; hHandle
0x18000e62d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000e632  call    cs:__imp_WaitForSingleObject
0x18000e638  mov     rcx, [rbx+58h]; hObject
0x18000e63c  call    cs:__imp_CloseHandle
0x18000e642  mov     rcx, [rbx+28h]; hObject
0x18000e646  call    cs:__imp_CloseHandle
0x18000e64c  mov     rcx, [rbx+30h]; hObject
0x18000e650  call    cs:__imp_CloseHandle
0x18000e656  mov     rcx, [rbx+60h]; hObject
0x18000e65a  call    cs:__imp_CloseHandle
0x18000e660  mov     rcx, [rbx+38h]; hObject
0x18000e664  call    cs:__imp_CloseHandle
0x18000e66a  mov     rcx, [rbx+40h]
0x18000e66e  add     rsp, 20h
0x18000e672  pop     rbx
0x18000e673  jmp     cs:__imp_CloseHandle
0x18000e67a  add     rsp, 20h
0x18000e67e  pop     rbx
0x18000e67f  retn
```
