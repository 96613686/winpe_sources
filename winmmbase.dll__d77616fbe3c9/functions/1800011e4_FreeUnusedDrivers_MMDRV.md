# FreeUnusedDrivers(_MMDRV *)

- ea: `0x1800011e4`
- end: `0x180001326`
- name: `?FreeUnusedDrivers@@YAXPEAU_MMDRV@@@Z`
- size: `322`
- prototype: `void __fastcall(struct _MMDRV *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180006ec0`

## callees

- `0x1800011e4`
- `0x180001cb0`
- `0x180002a20`
- `0x18000f5d8`
- `0x18001102a`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800012e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000130b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800012e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000130b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000127d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000127d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000129a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000129a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800012c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800012c1`

## pseudocode

```c
void __fastcall FreeUnusedDrivers(struct _MMDRV *a1)
{
  struct _MMDRV *v1; // rbx
  struct _MMDRV *v3; // rbp
  __int64 v4; // r9
  __int64 v5; // rsi

  v1 = *(struct _MMDRV **)a1;
  if ( *(struct _MMDRV **)a1 != a1 )
  {
    do
    {
      v3 = *(struct _MMDRV **)v1;
      if ( !*((_DWORD *)v1 + 22) && (*((_DWORD *)v1 + 28) & 1) == 0 )
      {
        v4 = *((_QWORD *)v1 + 13);
        if ( v4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids, v4);
          }
          (*((void (__fastcall **)(_QWORD, __int64, _QWORD))v1 + 10))(0, 101, 0);
        }
        v5 = *((_QWORD *)v1 + 4);
        EnterCriticalSection(&DriverListCritSec);
        if ( (int)v5 <= cInstalledDrivers )
        {
          LeaveCriticalSection(&DriverListCritSec);
          if ( InternalBroadcastDriverMessage((unsigned int)v5, 4, 0, 0) )
            InternalFreeDriver((unsigned int)v5);
        }
        else
        {
          LeaveCriticalSection(&DriverListCritSec);
        }
        DeleteCriticalSection((LPCRITICAL_SECTION)v1 + 3);
        **((_QWORD **)v1 + 1) = *(_QWORD *)v1;
        *(_QWORD *)(*(_QWORD *)v1 + 8LL) = *((_QWORD *)v1 + 1);
        HeapFree(hHeap, 0, *((LPVOID *)v1 + 13));
        memset_0(v1, 0, 0x120u);
        HeapFree(hHeap, 0, v1);
      }
      v1 = v3;
    }
    while ( v3 != a1 );
  }
}

```

## disassembly

```asm
0x1800011e4  push    rbx
0x1800011e6  push    rbp
0x1800011e7  push    rsi
0x1800011e8  push    rdi
0x1800011e9  sub     rsp, 38h
0x1800011ed  mov     rbx, [rcx]
0x1800011f0  mov     rdi, rcx
0x1800011f3  cmp     rbx, rcx
0x1800011f6  jz      loc_18000131D
0x1800011fc  cmp     dword ptr [rbx+58h], 0
0x180001200  mov     rbp, [rbx]
0x180001203  jnz     loc_180001311
0x180001209  mov     eax, [rbx+70h]
0x18000120c  test    al, 1
0x18000120e  jnz     loc_180001311
0x180001214  mov     r9, [rbx+68h]
0x180001218  test    r9, r9
0x18000121b  jz      short loc_180001272
0x18000121d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001224  lea     rax, WPP_GLOBAL_Control
0x18000122b  cmp     rcx, rax
0x18000122e  jz      short loc_180001254
0x180001230  test    dword ptr [rcx+1Ch], 400000h
0x180001237  jz      short loc_180001254
0x180001239  cmp     byte ptr [rcx+19h], 4
0x18000123d  jb      short loc_180001254
0x18000123f  mov     rcx, [rcx+10h]
0x180001243  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x18000124a  mov     edx, 0Ch
0x18000124f  call    WPP_SF_S
0x180001254  mov     rcx, [rbx+68h]
0x180001258  xor     r9d, r9d
0x18000125b  mov     rax, [rbx+50h]
0x18000125f  xor     r8d, r8d
0x180001262  mov     [rsp+58h+var_38], rcx
0x180001267  xor     ecx, ecx
0x180001269  lea     edx, [r9+65h]
0x18000126d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001272  mov     rsi, [rbx+20h]
0x180001276  lea     rcx, DriverListCritSec; lpCriticalSection
0x18000127d  call    cs:__imp_EnterCriticalSection
0x180001283  cmp     esi, cs:cInstalledDrivers
0x180001289  lea     rcx, DriverListCritSec; lpCriticalSection
0x180001290  jle     short loc_18000129A
0x180001292  call    cs:__imp_LeaveCriticalSection
0x180001298  jmp     short loc_1800012BD
0x18000129a  call    cs:__imp_LeaveCriticalSection
0x1800012a0  xor     r9d, r9d
0x1800012a3  xor     r8d, r8d
0x1800012a6  mov     ecx, esi
0x1800012a8  lea     edx, [r9+4]
0x1800012ac  call    InternalBroadcastDriverMessage
0x1800012b1  test    rax, rax
0x1800012b4  jz      short loc_1800012BD
0x1800012b6  mov     ecx, esi
0x1800012b8  call    InternalFreeDriver
0x1800012bd  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800012c1  call    cs:__imp_DeleteCriticalSection
0x1800012c7  mov     rcx, [rbx+8]
0x1800012cb  xor     edx, edx; dwFlags
0x1800012cd  mov     rax, [rbx]
0x1800012d0  mov     [rcx], rax
0x1800012d3  mov     rcx, [rbx]
0x1800012d6  mov     rax, [rbx+8]
0x1800012da  mov     [rcx+8], rax
0x1800012de  mov     r8, [rbx+68h]; lpMem
0x1800012e2  mov     rcx, cs:hHeap; hHeap
0x1800012e9  call    cs:__imp_HeapFree
0x1800012ef  xor     edx, edx; Val
0x1800012f1  mov     r8d, 120h; Size
0x1800012f7  mov     rcx, rbx; void *
0x1800012fa  call    memset_0
0x1800012ff  mov     rcx, cs:hHeap; hHeap
0x180001306  mov     r8, rbx; lpMem
0x180001309  xor     edx, edx; dwFlags
0x18000130b  call    cs:__imp_HeapFree
0x180001311  mov     rbx, rbp
0x180001314  cmp     rbp, rdi
0x180001317  jnz     loc_1800011FC
0x18000131d  add     rsp, 38h
0x180001321  pop     rdi
0x180001322  pop     rsi
0x180001323  pop     rbp
0x180001324  pop     rbx
0x180001325  retn
```
