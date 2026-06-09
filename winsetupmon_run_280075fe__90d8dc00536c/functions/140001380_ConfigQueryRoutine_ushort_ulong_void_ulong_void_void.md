# ConfigQueryRoutine(ushort *,ulong,void *,ulong,void *,void *)

- ea: `0x140001380`
- end: `0x1400013fb`
- name: `?ConfigQueryRoutine@@YAJPEAGKPEAXK11@Z`
- size: `123`
- prototype: `int(unsigned __int16 *, unsigned int, void *, unsigned int, void *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x140001380`
- `0x140003944`
- `0x14000a4b0`
- `0x14000a598`

## string_xrefs

- `0x1400013ca`: `Failed to deserialize tracking config from the registry (0x%08X)`

## pseudocode

```c
__int64 __fastcall ConfigQueryRoutine(
        unsigned __int16 *a1,
        int a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        void *a5,
        struct IWsmStableLogConfig **a6)
{
  unsigned int v6; // ebx
  int Instance; // eax

  if ( !a3 || !a4 || !a6 )
    return 0;
  v6 = 0;
  if ( a2 == 3 )
  {
    if ( *(_BYTE *)a6 == 1 )
    {
      return (unsigned int)CreateInstance(a3, a4, a6 + 1);
    }
    else if ( *(_BYTE *)a6 == 2 )
    {
      Instance = CreateInstance(a3, a4, a6 + 2);
      v6 = Instance;
      if ( Instance < 0 )
        WriteLogMessage(2, L"Failed to deserialize tracking config from the registry (0x%08X)", (unsigned int)Instance);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140001380  push    rbx
0x140001382  sub     rsp, 20h
0x140001386  mov     r10, r8
0x140001389  test    r8, r8
0x14000138c  jz      short loc_1400013F2
0x14000138e  test    r9d, r9d
0x140001391  jz      short loc_1400013F2
0x140001393  mov     r8, [rsp+28h+arg_28]
0x140001398  test    r8, r8
0x14000139b  jz      short loc_1400013F2
0x14000139d  xor     ebx, ebx
0x14000139f  cmp     edx, 3
0x1400013a2  jnz     short loc_1400013EE
0x1400013a4  movzx   ecx, byte ptr [r8]
0x1400013a8  sub     ecx, 1
0x1400013ab  jz      short loc_1400013DD
0x1400013ad  cmp     ecx, 1
0x1400013b0  jnz     short loc_1400013EE
0x1400013b2  add     r8, 10h; struct IWsmStableTrackingConfig **
0x1400013b6  mov     edx, r9d; unsigned int
0x1400013b9  mov     rcx, r10; unsigned __int8 *
0x1400013bc  call    ?CreateInstance@@YAJPEBEKPEAPEAVIWsmStableTrackingConfig@@@Z; CreateInstance(uchar const *,ulong,IWsmStableTrackingConfig * *)
0x1400013c1  mov     ebx, eax
0x1400013c3  test    eax, eax
0x1400013c5  jns     short loc_1400013EE
0x1400013c7  mov     r8d, eax
0x1400013ca  lea     rdx, aFailedToDeseri; "Failed to deserialize tracking config f"...
0x1400013d1  mov     ecx, 2
0x1400013d6  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400013db  jmp     short loc_1400013EE
0x1400013dd  add     r8, 8; struct IWsmStableLogConfig **
0x1400013e1  mov     edx, r9d; unsigned int
0x1400013e4  mov     rcx, r10; unsigned __int8 *
0x1400013e7  call    ?CreateInstance@@YAJPEBEKPEAPEAVIWsmStableLogConfig@@@Z; CreateInstance(uchar const *,ulong,IWsmStableLogConfig * *)
0x1400013ec  mov     ebx, eax
0x1400013ee  mov     eax, ebx
0x1400013f0  jmp     short loc_1400013F4
0x1400013f2  xor     eax, eax
0x1400013f4  add     rsp, 20h
0x1400013f8  pop     rbx
0x1400013f9  retn
```
