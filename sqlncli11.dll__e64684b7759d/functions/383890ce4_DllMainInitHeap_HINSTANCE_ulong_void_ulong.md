# DllMainInitHeap(HINSTANCE__ *,ulong,void *,ulong)

- ea: `0x383890ce4`
- end: `0x383890d65`
- name: `?DllMainInitHeap@@YAHPEAUHINSTANCE__@@KPEAXK@Z`
- size: `129`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3838924f8`

## callees

- `0x383890ce4`
- `0x38391aed0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3838f2d96`
- `KERNEL32!GetLastError` at `0x3838f2d96`
- `KERNEL32!HeapCreate` at `0x383890d12`
- `KERNEL32!HeapCreate` at `0x383890d12`
- `KERNEL32!HeapDestroy` at `0x3838f2ddd`
- `KERNEL32!HeapDestroy` at `0x3838f2ddd`
- `KERNEL32!GetProcessHeap` at `0x3838f2d67`
- `KERNEL32!GetProcessHeap` at `0x3838f2d67`
- `KERNEL32!HeapSetInformation` at `0x383890d40`
- `KERNEL32!HeapSetInformation` at `0x383890d40`

## pseudocode

```c
__int64 __fastcall DllMainInitHeap(HINSTANCE a1, int a2, void *a3)
{
  __int64 result; // rax
  int v4; // eax
  int HeapInformation; // [rsp+40h] [rbp+8h] BYREF

  if ( !(_DWORD)a1 )
  {
    if ( !g_fDisableMpHeap )
    {
      HeapDestroy(g_hHeapMalloc);
      g_hHeapMalloc = 0;
    }
    return 1;
  }
  if ( (_DWORD)a1 != 1 )
    return 1;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      g_fDisableMpHeap = 0;
      goto LABEL_6;
    }
    v4 = g_fDisableMpHeap;
  }
  else
  {
    v4 = 1;
    g_fDisableMpHeap = 1;
  }
  if ( v4 )
  {
    g_hHeapMalloc = GetProcessHeap();
    return 1;
  }
LABEL_6:
  result = (__int64)HeapCreate(2u, 0, 0);
  g_hHeapMalloc = (HANDLE)result;
  if ( result )
  {
    HeapInformation = 2;
    if ( HeapSetInformation((HANDLE)result, HeapCompatibilityInformation, &HeapInformation, 4u) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_383B4A1A8[0] )
          bidTraceW(off_383B434C8[0], 105472, off_383B4A1A8[0], g_hHeapMalloc);
      }
    }
    else if ( (bidGblFlags & 2) != 0 && off_383B4A1A0[0] )
    {
      GetLastError();
      bidTraceW(off_383B434C8[0], 110592, off_383B4A1A0[0], g_hHeapMalloc);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x383890ce4  sub     rsp, 38h
0x383890ce8  test    ecx, ecx
0x383890cea  jz      loc_3838F2DC9
0x383890cf0  dec     ecx
0x383890cf2  jnz     short loc_383890D5B
0x383890cf4  test    edx, edx
0x383890cf6  jz      loc_3838F2D54
0x383890cfc  dec     edx
0x383890cfe  jnz     loc_3838F2D4C
0x383890d04  and     cs:?g_fDisableMpHeap@@3HA, edx; int g_fDisableMpHeap
0x383890d0a  xor     edx, edx; dwInitialSize
0x383890d0c  xor     r8d, r8d; dwMaximumSize
0x383890d0f  lea     ecx, [rdx+2]; flOptions
0x383890d12  call    cs:__imp_HeapCreate
0x383890d18  mov     cs:?g_hHeapMalloc@@3PEAXEA, rax; void * g_hHeapMalloc
0x383890d1f  test    rax, rax
0x383890d22  jz      loc_3838F2DC4
0x383890d28  lea     r8, [rsp+38h+HeapInformation]; HeapInformation
0x383890d2d  mov     r9d, 4; HeapInformationLength
0x383890d33  xor     edx, edx; HeapInformationClass
0x383890d35  mov     rcx, rax; HeapHandle
0x383890d38  mov     [rsp+38h+HeapInformation], 2
0x383890d40  call    cs:__imp_HeapSetInformation
0x383890d46  test    eax, eax
0x383890d48  jz      loc_3838F2D79
0x383890d4e  test    byte ptr cs:_bidGblFlags, 2
0x383890d55  jnz     loc_3838F2D18
0x383890d5b  mov     eax, 1
0x383890d60  add     rsp, 38h
0x383890d64  retn
0x3838f2d18  mov     rax, cs:off_383B4A1A8; "<DllMainInitHeap|HEAP|INFO> LFH is enab"...
0x3838f2d1f  test    rax, rax
0x3838f2d22  jz      loc_383890D5B
0x3838f2d28  mov     r8, cs:off_383B4A1A8; "<DllMainInitHeap|HEAP|INFO> LFH is enab"...
0x3838f2d2f  mov     r9, cs:?g_hHeapMalloc@@3PEAXEA; void * g_hHeapMalloc
0x3838f2d36  mov     rcx, cs:off_383B434C8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838f2d3d  mov     edx, 19C00h
0x3838f2d42  call    _bidTraceW
0x3838f2d47  jmp     loc_383890D5B
0x3838f2d4c  mov     eax, cs:?g_fDisableMpHeap@@3HA; int g_fDisableMpHeap
0x3838f2d52  jmp     short loc_3838F2D5F
0x3838f2d54  mov     eax, 1
0x3838f2d59  mov     cs:?g_fDisableMpHeap@@3HA, eax; int g_fDisableMpHeap
0x3838f2d5f  test    eax, eax
0x3838f2d61  jz      loc_383890D0A
0x3838f2d67  call    cs:__imp_GetProcessHeap
0x3838f2d6d  mov     cs:?g_hHeapMalloc@@3PEAXEA, rax; void * g_hHeapMalloc
0x3838f2d74  jmp     loc_383890D5B
0x3838f2d79  test    byte ptr cs:_bidGblFlags, 2
0x3838f2d80  jz      loc_383890D5B
0x3838f2d86  mov     rax, cs:off_383B4A1A0; "<DllMainInitHeap|HEAP|INFO> LFH cannot "...
0x3838f2d8d  test    rax, rax
0x3838f2d90  jz      loc_383890D5B
0x3838f2d96  call    cs:__imp_GetLastError
0x3838f2d9c  mov     r8, cs:off_383B4A1A0; "<DllMainInitHeap|HEAP|INFO> LFH cannot "...
0x3838f2da3  mov     rcx, cs:off_383B434C8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838f2daa  mov     r9, cs:?g_hHeapMalloc@@3PEAXEA; void * g_hHeapMalloc
0x3838f2db1  mov     edx, 1B000h
0x3838f2db6  mov     [rsp+38h+var_18], eax
0x3838f2dba  call    _bidTraceW
0x3838f2dbf  jmp     loc_383890D5B
0x3838f2dc4  jmp     loc_383890D60
0x3838f2dc9  cmp     cs:?g_fDisableMpHeap@@3HA, 0; int g_fDisableMpHeap
0x3838f2dd0  jnz     loc_383890D5B
0x3838f2dd6  mov     rcx, cs:?g_hHeapMalloc@@3PEAXEA; hHeap
0x3838f2ddd  call    cs:__imp_HeapDestroy
0x3838f2de3  and     cs:?g_hHeapMalloc@@3PEAXEA, 0; void * g_hHeapMalloc
0x3838f2deb  jmp     loc_383890D5B
```
