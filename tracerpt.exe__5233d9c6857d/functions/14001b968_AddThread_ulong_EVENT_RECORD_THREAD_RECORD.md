# AddThread(ulong,_EVENT_RECORD *,_THREAD_RECORD * *)

- ea: `0x14001b968`
- end: `0x14001ba3f`
- name: `?AddThread@@YAEKPEAU_EVENT_RECORD@@PEAPEAU_THREAD_RECORD@@@Z`
- size: `215`
- prototype: `unsigned __int8 __fastcall(unsigned int, struct _EVENT_RECORD *, struct _THREAD_RECORD **)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400033c0`
- `0x140006588`
- `0x1400069c8`
- `0x1400078ec`
- `0x140009d78`
- `0x140009ea8`
- `0x14000a0d4`

## callees

- `0x14001b968`
- `0x1400400d6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b979`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b979`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001b98d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001b98d`

## pseudocode

```c
unsigned __int8 __fastcall AddThread(unsigned int a1, struct _EVENT_RECORD *a2, struct _THREAD_RECORD **a3)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  LARGE_INTEGER TimeStamp; // rax
  __int64 v10; // rdx

  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, 0x238u);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, 0x238u);
    v8[3] = v8 + 2;
    v8[2] = v8 + 2;
    v8[5] = v8 + 4;
    v8[4] = v8 + 4;
    v8[7] = v8 + 6;
    v8[6] = v8 + 6;
    v8[9] = v8 + 8;
    v8[8] = v8 + 8;
    TimeStamp = a2->EventHeader.TimeStamp;
    v8[22] = TimeStamp.QuadPart;
    v8[21] = TimeStamp.QuadPart;
    *((_DWORD *)v8 + 20) = a1;
    *((_DWORD *)v8 + 28) = a2->BufferContext.ProcessorNumber;
    v10 = qword_140082128 + 16LL * (a1 % 0x1D);
    v7 = *(_QWORD **)v10;
    if ( *(_QWORD *)(*(_QWORD *)v10 + 8LL) != v10 )
      __fastfail(3u);
    *v8 = v7;
    v8[1] = v10;
    v7[1] = v8;
    LOBYTE(v7) = 1;
    *(_QWORD *)v10 = v8;
    *a3 = (struct _THREAD_RECORD *)v8;
  }
  return (unsigned __int8)v7;
}

```

## disassembly

```asm
0x14001b968  push    rbx
0x14001b96a  push    rbp
0x14001b96b  push    rsi
0x14001b96c  push    rdi
0x14001b96d  sub     rsp, 28h
0x14001b971  mov     rdi, r8
0x14001b974  mov     rbp, rdx
0x14001b977  mov     esi, ecx
0x14001b979  call    cs:__imp_GetProcessHeap
0x14001b97f  mov     edx, 8; dwFlags
0x14001b984  mov     r8d, 238h; dwBytes
0x14001b98a  mov     rcx, rax; hHeap
0x14001b98d  call    cs:__imp_HeapAlloc
0x14001b993  mov     rbx, rax
0x14001b996  test    rax, rax
0x14001b999  jz      loc_14001BA36
0x14001b99f  xor     edx, edx; Val
0x14001b9a1  mov     r8d, 238h; Size
0x14001b9a7  mov     rcx, rbx; void *
0x14001b9aa  call    memset_0
0x14001b9af  lea     rax, [rbx+10h]
0x14001b9b3  mov     [rax+8], rax
0x14001b9b7  mov     [rax], rax
0x14001b9ba  lea     rax, [rbx+20h]
0x14001b9be  mov     [rax+8], rax
0x14001b9c2  mov     [rax], rax
0x14001b9c5  lea     rax, [rbx+30h]
0x14001b9c9  mov     [rax+8], rax
0x14001b9cd  mov     [rax], rax
0x14001b9d0  lea     rax, [rbx+40h]
0x14001b9d4  mov     [rax+8], rax
0x14001b9d8  mov     [rax], rax
0x14001b9db  mov     rax, [rbp+10h]
0x14001b9df  mov     [rbx+0B0h], rax
0x14001b9e6  mov     [rbx+0A8h], rax
0x14001b9ed  mov     [rbx+50h], esi
0x14001b9f0  movzx   eax, byte ptr [rbp+50h]
0x14001b9f4  mov     [rbx+70h], eax
0x14001b9f7  mov     eax, 8D3DCB09h
0x14001b9fc  mul     esi
0x14001b9fe  shr     edx, 4
0x14001ba01  imul    eax, edx, 1Dh
0x14001ba04  sub     esi, eax
0x14001ba06  mov     edx, esi
0x14001ba08  shl     rdx, 4
0x14001ba0c  add     rdx, cs:qword_140082128
0x14001ba13  mov     rax, [rdx]
0x14001ba16  cmp     [rax+8], rdx
0x14001ba1a  jz      short loc_14001BA23
0x14001ba1c  mov     ecx, 3
0x14001ba21  int     29h; Win8: RtlFailFast(ecx)
0x14001ba23  mov     [rbx], rax
0x14001ba26  mov     [rbx+8], rdx
0x14001ba2a  mov     [rax+8], rbx
0x14001ba2e  mov     al, 1
0x14001ba30  mov     [rdx], rbx
0x14001ba33  mov     [rdi], rbx
0x14001ba36  add     rsp, 28h
0x14001ba3a  pop     rdi
0x14001ba3b  pop     rsi
0x14001ba3c  pop     rbp
0x14001ba3d  pop     rbx
0x14001ba3e  retn
```
