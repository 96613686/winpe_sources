# CDVRSink::Write(uchar *,ulong,ulong *)

- ea: `0x180005160`
- end: `0x1800051b7`
- name: `?Write@CDVRSink@@MEAAJPEAEKPEAK@Z`
- size: `87`
- prototype: `__int64 __fastcall(CDVRSink *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005160`
- `0x18000c1b0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CDVRSink::Write(CUnbufferedWriter **this, unsigned __int8 *a2, unsigned int a3, unsigned int *a4)
{
  __int64 result; // rax
  unsigned __int8 *v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = a3;
  v6 = a2;
  if ( !this[1199] )
    return CWMFileSinkV1::Write(this, a2, a3, a4);
  *a4 = a3;
  result = (*(__int64 (__fastcall **)(CUnbufferedWriter *, unsigned __int8 **, unsigned int *))(*(_QWORD *)this[1199]
                                                                                              + 48LL))(
             this[1199],
             &v6,
             &v7);
  if ( (int)result < 0 )
  {
    *a4 = 0;
    return 3222077464LL;
  }
  return result;
}

```

## disassembly

```asm
0x180005160  mov     r11, rsp
0x180005163  mov     [r11+18h], r8d
0x180005167  mov     [r11+10h], rdx
0x18000516b  push    rbx
0x18000516c  sub     rsp, 20h
0x180005170  cmp     qword ptr [rcx+2578h], 0
0x180005178  mov     rbx, r9
0x18000517b  jz      short loc_1800051AC
0x18000517d  mov     [r9], r8d
0x180005180  lea     rdx, [r11+10h]
0x180005184  mov     rcx, [rcx+2578h]
0x18000518b  lea     r8, [r11+18h]
0x18000518f  mov     rax, [rcx]
0x180005192  mov     rax, [rax+30h]
0x180005196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000519b  test    eax, eax
0x18000519d  jns     short loc_1800051B1
0x18000519f  mov     dword ptr [rbx], 0
0x1800051a5  mov     eax, 0C00D0018h
0x1800051aa  jmp     short loc_1800051B1
0x1800051ac  call    ?Write@CWMFileSinkV1@@MEAAJPEAEKPEAK@Z; CWMFileSinkV1::Write(uchar *,ulong,ulong *)
0x1800051b1  add     rsp, 20h
0x1800051b5  pop     rbx
0x1800051b6  retn
```
