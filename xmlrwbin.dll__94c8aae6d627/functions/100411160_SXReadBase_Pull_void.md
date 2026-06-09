# SXReadBase::Pull(void)

- ea: `0x100411160`
- end: `0x10041125a`
- name: `?Pull@SXReadBase@@AEAA_NXZ`
- size: `250`
- prototype: `bool __fastcall(SXReadBase *__hidden this)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x100404f80`
- `0x100406be0`
- `0x10040edb0`
- `0x10040f700`
- `0x10040f9a0`
- `0x10040fbf0`
- `0x1004101e0`
- `0x100411000`

## callees

- `0x100401350`
- `0x100411160`
- `0x100411260`
- `0x100415d60`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004111b7`
- `KERNEL32!HeapAlloc` at `0x1004111b7`

## pseudocode

```c
bool __fastcall SXReadBase::Pull(SXReadBase *this)
{
  char *v1; // rax
  struct IMalloc *v3; // rcx
  const void *v4; // rdx
  __int64 v5; // r8
  char *v6; // rcx
  size_t v7; // r8
  unsigned int v8; // eax

  v1 = (char *)*((_QWORD *)this + 177);
  if ( v1 )
  {
    v4 = (const void *)*((_QWORD *)this + 178);
    v5 = *((_QWORD *)this + 179);
    v6 = (char *)*((_QWORD *)this + 177);
    v7 = v5 - (_QWORD)v4;
    if ( v7 )
    {
      memmove(v6, v4, v7);
      v1 = (char *)*((_QWORD *)this + 177);
      v6 = &v1[*((_QWORD *)this + 179) - *((_QWORD *)this + 178)];
    }
    *((_QWORD *)this + 179) = v6;
  }
  else
  {
    *((_DWORD *)this + 353) = 2048;
    v3 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v3 || (v3 = g_pMalloc) != 0 )
      v1 = (char *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v3->lpVtbl->Alloc)(v3, 2048);
    else
      v1 = (char *)HeapAlloc(g_hHeap, 0, 0x800u);
    if ( !v1 )
    {
      MXRRaiseException(-2147024882);
      JUMPOUT(0x100411259LL);
    }
    *((_QWORD *)this + 177) = v1;
    *((_QWORD *)this + 179) = v1;
  }
  *((_QWORD *)this + 178) = v1;
  v8 = SXReadBase::Read(
         this,
         *((unsigned __int8 **)this + 179),
         *((_DWORD *)this + 354) + *((_DWORD *)this + 353) - *((_DWORD *)this + 358));
  *((_QWORD *)this + 179) += v8;
  return v8 != 0;
}

```

## disassembly

```asm
0x100411160  push    rbx
0x100411162  sub     rsp, 20h
0x100411166  mov     rax, [rcx+588h]
0x10041116d  mov     rbx, rcx
0x100411170  test    rax, rax
0x100411173  jnz     short loc_1004111D6
0x100411175  mov     dword ptr [rcx+584h], 800h
0x10041117f  mov     rcx, [rcx+8]
0x100411183  test    rcx, rcx
0x100411186  jnz     short loc_100411194
0x100411188  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041118f  test    rcx, rcx
0x100411192  jz      short loc_1004111A8
0x100411194  mov     rax, [rcx]
0x100411197  mov     edx, 800h
0x10041119c  mov     rax, [rax+18h]
0x1004111a0  call    cs:__guard_dispatch_icall_fptr
0x1004111a6  jmp     short loc_1004111BD
0x1004111a8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004111af  xor     edx, edx; dwFlags
0x1004111b1  mov     r8d, 800h; dwBytes
0x1004111b7  call    cs:__imp_HeapAlloc
0x1004111bd  test    rax, rax
0x1004111c0  jz      loc_10041124F
0x1004111c6  mov     [rbx+588h], rax
0x1004111cd  mov     [rbx+598h], rax
0x1004111d4  jmp     short loc_100411210
0x1004111d6  mov     rdx, [rcx+590h]; Src
0x1004111dd  mov     r8, [rcx+598h]
0x1004111e4  mov     rcx, rax; void *
0x1004111e7  sub     r8, rdx; Size
0x1004111ea  jz      short loc_100411209
0x1004111ec  call    memmove
0x1004111f1  mov     rcx, [rbx+598h]
0x1004111f8  sub     rcx, [rbx+590h]
0x1004111ff  mov     rax, [rbx+588h]
0x100411206  add     rcx, rax
0x100411209  mov     [rbx+598h], rcx
0x100411210  mov     [rbx+590h], rax
0x100411217  mov     rcx, rbx; this
0x10041121a  mov     r8d, [rbx+584h]
0x100411221  sub     r8d, [rbx+598h]
0x100411228  add     r8d, [rbx+588h]; unsigned int
0x10041122f  mov     rdx, [rbx+598h]; unsigned __int8 *
0x100411236  call    ?Read@SXReadBase@@AEAAKPEAEK@Z; SXReadBase::Read(uchar *,ulong)
0x10041123b  mov     ecx, eax
0x10041123d  add     [rbx+598h], rcx
0x100411244  test    eax, eax
0x100411246  setnz   al
0x100411249  add     rsp, 20h
0x10041124d  pop     rbx
0x10041124e  retn
0x10041124f  mov     ecx, 8007000Eh; int
0x100411254  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
