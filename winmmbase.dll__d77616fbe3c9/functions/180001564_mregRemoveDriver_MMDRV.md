# mregRemoveDriver(_MMDRV *)

- ea: `0x180001564`
- end: `0x18000164c`
- name: `?mregRemoveDriver@@YAXPEAU_MMDRV@@@Z`
- size: `232`
- prototype: `void __fastcall(struct _MMDRV *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800048e0`
- `0x180005030`
- `0x180007d70`

## callees

- `0x180001514`
- `0x180001564`
- `0x180001cb0`
- `0x180002558`
- `0x180002a20`
- `0x18001102a`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001619`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001619`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001645`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000159f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000159f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800015b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800015bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800015b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800015bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800015f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800015f8`

## pseudocode

```c
void __fastcall mregRemoveDriver(struct _MMDRV *a1)
{
  __int64 v2; // rdi
  void *v3; // r8

  StringIdDict_Remove(a1);
  (*((void (__fastcall **)(_QWORD, __int64, _QWORD))a1 + 10))(0, 101, 0);
  v2 = *((_QWORD *)a1 + 4);
  EnterCriticalSection(&DriverListCritSec);
  if ( (int)v2 <= cInstalledDrivers )
  {
    LeaveCriticalSection(&DriverListCritSec);
    if ( InternalBroadcastDriverMessage((unsigned int)v2, 4, 0, 0) )
      InternalFreeDriver((unsigned int)v2);
  }
  else
  {
    LeaveCriticalSection(&DriverListCritSec);
  }
  **((_QWORD **)a1 + 1) = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *((_QWORD *)a1 + 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)a1 + 3);
  wdmDevInterfaceDec(*((_QWORD *)a1 + 12));
  v3 = (void *)*((_QWORD *)a1 + 13);
  if ( v3 )
    HeapFree(hHeap, 0, v3);
  memset_0(a1, 0, 0x120u);
  HeapFree(hHeap, 0, a1);
}

```

## disassembly

```asm
0x180001564  mov     [rsp+arg_0], rbx
0x180001569  push    rdi
0x18000156a  sub     rsp, 30h
0x18000156e  mov     rbx, rcx
0x180001571  call    ?StringIdDict_Remove@@YAXPEAU_MMDRV@@@Z; StringIdDict_Remove(_MMDRV *)
0x180001576  mov     rdx, [rcx+68h]
0x18000157a  xor     r9d, r9d
0x18000157d  mov     rax, [rbx+50h]
0x180001581  xor     r8d, r8d
0x180001584  mov     [rsp+38h+var_18], rdx
0x180001589  xor     ecx, ecx
0x18000158b  lea     edx, [r9+65h]
0x18000158f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001594  mov     rdi, [rbx+20h]
0x180001598  lea     rcx, DriverListCritSec; lpCriticalSection
0x18000159f  call    cs:__imp_EnterCriticalSection
0x1800015a5  cmp     edi, cs:cInstalledDrivers
0x1800015ab  lea     rcx, DriverListCritSec; lpCriticalSection
0x1800015b2  jle     short loc_1800015BC
0x1800015b4  call    cs:__imp_LeaveCriticalSection
0x1800015ba  jmp     short loc_1800015DF
0x1800015bc  call    cs:__imp_LeaveCriticalSection
0x1800015c2  xor     r9d, r9d
0x1800015c5  xor     r8d, r8d
0x1800015c8  mov     ecx, edi
0x1800015ca  lea     edx, [r9+4]
0x1800015ce  call    InternalBroadcastDriverMessage
0x1800015d3  test    rax, rax
0x1800015d6  jz      short loc_1800015DF
0x1800015d8  mov     ecx, edi
0x1800015da  call    InternalFreeDriver
0x1800015df  mov     rcx, [rbx+8]
0x1800015e3  mov     rax, [rbx]
0x1800015e6  mov     [rcx], rax
0x1800015e9  mov     rcx, [rbx]
0x1800015ec  mov     rax, [rbx+8]
0x1800015f0  mov     [rcx+8], rax
0x1800015f4  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800015f8  call    cs:__imp_DeleteCriticalSection
0x1800015fe  mov     rcx, [rbx+60h]
0x180001602  call    wdmDevInterfaceDec
0x180001607  mov     r8, [rbx+68h]; lpMem
0x18000160b  test    r8, r8
0x18000160e  jz      short loc_18000161F
0x180001610  mov     rcx, cs:hHeap; hHeap
0x180001617  xor     edx, edx; dwFlags
0x180001619  call    cs:__imp_HeapFree
0x18000161f  xor     edx, edx; Val
0x180001621  mov     r8d, 120h; Size
0x180001627  mov     rcx, rbx; void *
0x18000162a  call    memset_0
0x18000162f  mov     rcx, cs:hHeap
0x180001636  mov     r8, rbx
0x180001639  xor     edx, edx
0x18000163b  mov     rbx, [rsp+38h+arg_0]
0x180001640  add     rsp, 30h
0x180001644  pop     rdi
0x180001645  jmp     cs:__imp_HeapFree
```
