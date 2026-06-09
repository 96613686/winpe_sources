# MpGetProcessContextByObject

- ea: `0x14003a1b0`
- end: `0x14003a2b4`
- name: `MpGetProcessContextByObject`
- size: `260`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `43`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001550`
- `0x140002080`
- `0x14000dc18`
- `0x14002c980`
- `0x14002d520`
- `0x14002e3c4`
- `0x14002e850`
- `0x14002f9f0`
- `0x14002fe00`
- `0x1400393f0`
- `0x140039f70`
- `0x14003a660`
- `0x14003be04`
- `0x14003c7b0`
- `0x14003c990`
- `0x14003dd40`
- `0x1400443c0`
- `0x140044e6c`
- `0x1400451c0`
- `0x140045670`
- `0x1400459c0`
- `0x140047ad0`
- `0x1400496d8`
- `0x140049ec0`
- `0x14004a758`
- `0x14004a930`
- `0x14004b990`
- `0x14004dda0`
- `0x140062588`
- `0x140063a18`
- `0x14006de7c`
- `0x14006e4f4`
- `0x14006eba0`
- `0x14006f0d8`
- `0x1400740f0`
- `0x14007ab88`
- `0x14007da0c`
- `0x14007e188`
- `0x14007e274`
- `0x14007ea68`
- `0x14007f16c`
- `0x140080e40`
- `0x140081bd0`

## callees

- `0x14003a1b0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14003a1e2`
- `ntoskrnl!PsGetProcessId` at `0x14003a1e2`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003a1d0`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003a1d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003a28a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003a28a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a27e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a27e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003a21f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003a21f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003a20d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003a20d`

## pseudocode

```c
__int64 __fastcall MpGetProcessContextByObject(PEPROCESS Process, volatile signed __int32 **a2)
{
  LONGLONG TimeQuadPart; // rbp
  HANDLE ProcessId; // rax
  unsigned int v6; // esi
  unsigned __int64 v7; // rdi
  char *v8; // rbx
  _QWORD *v9; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v11; // rcx

  TimeQuadPart = PsGetProcessCreateTimeQuadPart(Process);
  ProcessId = PsGetProcessId(Process);
  v6 = -1073741275;
  *a2 = 0;
  v7 = (unsigned __int64)ProcessId;
  if ( ProcessId )
  {
    v8 = (char *)MpProcessTable;
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)(v8 + 8), 1u);
    v9 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((v7 >> 2) & 0x7F));
    for ( i = (_QWORD *)*v9; i != v9; i = (_QWORD *)*i )
    {
      v11 = (volatile signed __int32 *)(i - 1);
      if ( v7 == i[2] && TimeQuadPart == *((_QWORD *)v11 + 4) )
      {
        _InterlockedIncrement(v11 + 12);
        *a2 = v11;
        v6 = 0;
        break;
      }
    }
    ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
    KeLeaveCriticalRegion();
  }
  return v6;
}

```

## disassembly

```asm
0x14003a1b0  mov     [rsp+arg_0], rbx
0x14003a1b5  mov     [rsp+arg_8], rbp
0x14003a1ba  mov     [rsp+arg_10], rsi
0x14003a1bf  mov     [rsp+arg_18], rdi
0x14003a1c4  push    r14
0x14003a1c6  sub     rsp, 20h
0x14003a1ca  mov     r14, rdx
0x14003a1cd  mov     rbx, rcx
0x14003a1d0  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14003a1d7  nop     dword ptr [rax+rax+00h]
0x14003a1dc  mov     rcx, rbx; Process
0x14003a1df  mov     rbp, rax
0x14003a1e2  call    cs:__imp_PsGetProcessId
0x14003a1e9  nop     dword ptr [rax+rax+00h]
0x14003a1ee  mov     esi, 0C0000225h
0x14003a1f3  mov     qword ptr [r14], 0
0x14003a1fa  mov     rdi, rax
0x14003a1fd  test    rax, rax
0x14003a200  jz      loc_14003A296
0x14003a206  mov     rbx, cs:MpProcessTable
0x14003a20d  call    cs:__imp_KeEnterCriticalRegion
0x14003a214  nop     dword ptr [rax+rax+00h]
0x14003a219  mov     dl, 1; Wait
0x14003a21b  lea     rcx, [rbx+8]; Resource
0x14003a21f  call    cs:__imp_ExAcquireResourceSharedLite
0x14003a226  nop     dword ptr [rax+rax+00h]
0x14003a22b  mov     rax, cs:MpProcessTable
0x14003a232  mov     r8, rdi
0x14003a235  shr     r8, 2
0x14003a239  and     r8d, 7Fh
0x14003a23d  shl     r8, 4
0x14003a241  add     r8, [rax+180h]
0x14003a248  mov     rax, [r8]
0x14003a24b  nop     dword ptr [rax+rax+00h]
0x14003a250  cmp     rax, r8
0x14003a253  jz      short loc_14003A273
0x14003a255  cmp     rdi, [rax+10h]
0x14003a259  lea     rcx, [rax-8]
0x14003a25d  jz      short loc_14003A264
0x14003a25f  mov     rax, [rax]
0x14003a262  jmp     short loc_14003A250
0x14003a264  cmp     rbp, [rcx+20h]
0x14003a268  jnz     short loc_14003A25F
0x14003a26a  lock inc dword ptr [rcx+30h]
0x14003a26e  mov     [r14], rcx
0x14003a271  xor     esi, esi
0x14003a273  mov     rcx, cs:MpProcessTable
0x14003a27a  add     rcx, 8; Resource
0x14003a27e  call    cs:__imp_ExReleaseResourceLite
0x14003a285  nop     dword ptr [rax+rax+00h]
0x14003a28a  call    cs:__imp_KeLeaveCriticalRegion
0x14003a291  nop     dword ptr [rax+rax+00h]
0x14003a296  mov     rbx, [rsp+28h+arg_0]
0x14003a29b  mov     eax, esi
0x14003a29d  mov     rsi, [rsp+28h+arg_10]
0x14003a2a2  mov     rbp, [rsp+28h+arg_8]
0x14003a2a7  mov     rdi, [rsp+28h+arg_18]
0x14003a2ac  add     rsp, 20h
0x14003a2b0  pop     r14
0x14003a2b2  retn
```
