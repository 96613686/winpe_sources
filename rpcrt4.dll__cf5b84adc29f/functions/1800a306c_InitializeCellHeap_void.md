# InitializeCellHeap(void)

- ea: `0x1800a306c`
- end: `0x1800a3138`
- name: `?InitializeCellHeap@@YAJXZ`
- size: `204`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800258b4`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800a306c`
- `0x1800a7f30`
- `0x1800bc088`

## import_xrefs

- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x1800a3095`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x1800a3095`
- `ntdll!RtlFreeUnicodeString` at `0x1800a3119`
- `ntdll!RtlFreeUnicodeString` at `0x1800a3119`

## pseudocode

```c
__int64 InitializeCellHeap(void)
{
  unsigned int v0; // ebx
  CellHeap *v1; // rax
  struct CellHeap *v2; // rax
  struct CellHeap *v3; // rdi
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  v6 = 0;
  UnicodeString = 0;
  if ( (int)RtlGetAppContainerNamedObjectPath(0, 0, 0, &UnicodeString) < 0 || UnicodeString.Length )
  {
    v0 = 1764;
    goto LABEL_11;
  }
  if ( !g_pCellHeap )
  {
    v1 = (CellHeap *)AllocWrapper(0x88u);
    if ( v1 )
    {
      v2 = CellHeap::CellHeap(v1, &v6);
      g_pCellHeap = v2;
      v3 = v2;
      if ( v2 )
      {
        v0 = v6;
        if ( v6 )
        {
          CellHeap::~CellHeap(v2);
          FreeWrapper(v3);
          g_pCellHeap = 0;
        }
        goto LABEL_11;
      }
    }
    else
    {
      g_pCellHeap = 0;
    }
    v0 = 14;
  }
LABEL_11:
  RtlFreeUnicodeString(&UnicodeString);
  return v0;
}

```

## disassembly

```asm
0x1800a306c  mov     rax, rsp
0x1800a306f  mov     [rax+10h], rbx
0x1800a3073  mov     [rax+18h], rsi
0x1800a3077  push    rdi
0x1800a3078  sub     rsp, 30h
0x1800a307c  xorps   xmm0, xmm0
0x1800a307f  lea     r9, [rax-18h]
0x1800a3083  xor     esi, esi
0x1800a3085  xor     r8d, r8d
0x1800a3088  mov     ebx, esi
0x1800a308a  xor     edx, edx
0x1800a308c  xor     ecx, ecx
0x1800a308e  mov     [rax+8], ebx
0x1800a3091  movups  xmmword ptr [rax-18h], xmm0
0x1800a3095  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x1800a309c  nop     dword ptr [rax+rax+00h]
0x1800a30a1  test    eax, eax
0x1800a30a3  js      short loc_1800A310F
0x1800a30a5  cmp     [rsp+38h+UnicodeString.Length], si
0x1800a30aa  jnz     short loc_1800A310F
0x1800a30ac  cmp     cs:?g_pCellHeap@@3PEAVCellHeap@@EA, rsi; CellHeap * g_pCellHeap
0x1800a30b3  jnz     short loc_1800A3114
0x1800a30b5  mov     ecx, 88h; dwBytes
0x1800a30ba  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a30bf  test    rax, rax
0x1800a30c2  jz      short loc_1800A3101
0x1800a30c4  lea     rdx, [rsp+38h+arg_0]; int *
0x1800a30c9  mov     rcx, rax; this
0x1800a30cc  call    ??0CellHeap@@QEAA@PEAJ@Z; CellHeap::CellHeap(long *)
0x1800a30d1  mov     cs:?g_pCellHeap@@3PEAVCellHeap@@EA, rax; CellHeap * g_pCellHeap
0x1800a30d8  mov     rdi, rax
0x1800a30db  test    rax, rax
0x1800a30de  jz      short loc_1800A3108
0x1800a30e0  mov     ebx, [rsp+38h+arg_0]
0x1800a30e4  test    ebx, ebx
0x1800a30e6  jz      short loc_1800A3114
0x1800a30e8  mov     rcx, rax; this
0x1800a30eb  call    ??1CellHeap@@QEAA@XZ; CellHeap::~CellHeap(void)
0x1800a30f0  mov     rcx, rdi; lpMem
0x1800a30f3  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a30f8  mov     cs:?g_pCellHeap@@3PEAVCellHeap@@EA, rsi; CellHeap * g_pCellHeap
0x1800a30ff  jmp     short loc_1800A3114
0x1800a3101  mov     cs:?g_pCellHeap@@3PEAVCellHeap@@EA, rsi; CellHeap * g_pCellHeap
0x1800a3108  mov     ebx, 0Eh
0x1800a310d  jmp     short loc_1800A3114
0x1800a310f  mov     ebx, 6E4h
0x1800a3114  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x1800a3119  call    cs:__imp_RtlFreeUnicodeString
0x1800a3120  nop     dword ptr [rax+rax+00h]
0x1800a3125  mov     rsi, [rsp+38h+arg_10]
0x1800a312a  mov     eax, ebx
0x1800a312c  mov     rbx, [rsp+38h+arg_8]
0x1800a3131  add     rsp, 30h
0x1800a3135  pop     rdi
0x1800a3136  retn
```
