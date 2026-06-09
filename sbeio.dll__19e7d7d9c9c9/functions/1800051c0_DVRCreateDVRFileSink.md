# DVRCreateDVRFileSink

- ea: `0x1800051c0`
- end: `0x1800052a4`
- name: `DVRCreateDVRFileSink`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011a0`
- `0x180001f94`
- `0x1800051c0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall DVRCreateDVRFileSink(__int64 a1, __int64 a2, int a3, __int64 a4, unsigned int a5, _QWORD *a6)
{
  void *v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rax
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  int v14; // edi
  int v15[14]; // [rsp+40h] [rbp-38h] BYREF

  v15[0] = 0;
  if ( !a6 )
    return 2147500035LL;
  *a6 = 0;
  v11 = operator new(0x2638u);
  if ( !v11 )
    return 2147942414LL;
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))CDVRSink::CDVRSink((__int64)v11, a1, a2, a3, a4, a5, v15);
  v13 = v12;
  if ( !v12 )
    return 2147942414LL;
  v14 = v15[0];
  if ( v15[0] < 0 || (v14 = (**v12)(v12, &IID_IDVRFileSink, a6), v14 < 0) )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
    *a6 = 0;
  }
  else
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800051c0  push    rbx
0x1800051c2  push    rbp
0x1800051c3  push    rsi
0x1800051c4  push    rdi
0x1800051c5  push    r14
0x1800051c7  sub     rsp, 50h
0x1800051cb  mov     rsi, [rsp+78h+arg_28]
0x1800051d3  mov     rbx, r9
0x1800051d6  mov     [rsp+78h+var_38], 0
0x1800051de  mov     edi, r8d
0x1800051e1  mov     rbp, rdx
0x1800051e4  mov     r14, rcx
0x1800051e7  test    rsi, rsi
0x1800051ea  jnz     short loc_1800051F6
0x1800051ec  mov     eax, 80004003h
0x1800051f1  jmp     loc_180005299
0x1800051f6  mov     ecx, 2638h; Size
0x1800051fb  mov     qword ptr [rsi], 0
0x180005202  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005207  test    rax, rax
0x18000520a  jz      loc_180005294
0x180005210  lea     rcx, [rsp+78h+var_38]
0x180005215  mov     r9d, edi
0x180005218  mov     [rsp+78h+var_48], rcx
0x18000521d  mov     r8, rbp
0x180005220  mov     ecx, [rsp+78h+arg_20]
0x180005227  mov     rdx, r14
0x18000522a  mov     [rsp+78h+var_50], ecx
0x18000522e  mov     rcx, rax
0x180005231  mov     [rsp+78h+var_58], rbx
0x180005236  call    ??0CDVRSink@@QEAA@PEAUHKEY__@@0KPEAPEAXHPEAJPEAV?$CTPtrArray@UWRITER_SINK_CALLBACK@@$0BE@@@@Z; CDVRSink::CDVRSink(HKEY__ *,HKEY__ *,ulong,void * *,int,long *,CTPtrArray<WRITER_SINK_CALLBACK,20> *)
0x18000523b  mov     rbx, rax
0x18000523e  test    rax, rax
0x180005241  jz      short loc_180005294
0x180005243  mov     edi, [rsp+78h+var_38]
0x180005247  test    edi, edi
0x180005249  js      short loc_18000527A
0x18000524b  mov     rcx, [rax]
0x18000524e  lea     rdx, IID_IDVRFileSink
0x180005255  mov     r8, rsi
0x180005258  mov     rax, [rcx]
0x18000525b  mov     rcx, rbx
0x18000525e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005263  mov     edi, eax
0x180005265  test    eax, eax
0x180005267  js      short loc_18000527A
0x180005269  mov     rax, [rbx]
0x18000526c  mov     rcx, rbx
0x18000526f  mov     rax, [rax+10h]
0x180005273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005278  jmp     short loc_180005290
0x18000527a  mov     rcx, [rbx]
0x18000527d  mov     rax, [rcx+10h]
0x180005281  mov     rcx, rbx
0x180005284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005289  mov     qword ptr [rsi], 0
0x180005290  mov     eax, edi
0x180005292  jmp     short loc_180005299
0x180005294  mov     eax, 8007000Eh
0x180005299  add     rsp, 50h
0x18000529d  pop     r14
0x18000529f  pop     rdi
0x1800052a0  pop     rsi
0x1800052a1  pop     rbp
0x1800052a2  pop     rbx
0x1800052a3  retn
```
