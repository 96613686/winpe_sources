# CASFMMStream::GetNextObject(CASFLonghandObject * *,void * &)

- ea: `0x180012ff4`
- end: `0x180013031`
- name: `?GetNextObject@CASFMMStream@@QEAAJPEAPEAVCASFLonghandObject@@AEAPEAX@Z`
- size: `61`
- prototype: `int(CASFMMStream *__hidden this, struct CASFLonghandObject **, void **)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180004ed0`
- `0x1800087a0`
- `0x180008cc0`
- `0x180009d80`
- `0x18000b780`
- `0x18000bddc`
- `0x18000c2a0`

## callees

- `0x180012fbc`
- `0x180012ff4`

## pseudocode

```c
__int64 __fastcall CASFMMStream::GetNextObject(CASFMMStream *this, struct CASFLonghandObject **a2, void **a3)
{
  __int64 v3; // r8

  if ( !a2 || !*a3 )
    return 2147942487LL;
  if ( !(unsigned int)CVPtrList::GetNext(this, a3, (void **)a2) )
    return 2147500037LL;
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v3 + 48LL));
  return 0;
}

```

## disassembly

```asm
0x180012ff4  sub     rsp, 28h
0x180012ff8  mov     rax, r8
0x180012ffb  mov     r8, rdx; void **
0x180012ffe  test    rdx, rdx
0x180013001  jz      short loc_180013027
0x180013003  cmp     qword ptr [rax], 0
0x180013007  jz      short loc_180013027
0x180013009  mov     rdx, rax; void **
0x18001300c  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x180013011  test    eax, eax
0x180013013  jnz     short loc_18001301C
0x180013015  mov     eax, 80004005h
0x18001301a  jmp     short loc_18001302C
0x18001301c  mov     rax, [r8]
0x18001301f  lock inc dword ptr [rax+30h]
0x180013023  xor     eax, eax
0x180013025  jmp     short loc_18001302C
0x180013027  mov     eax, 80070057h
0x18001302c  add     rsp, 28h
0x180013030  retn
```
