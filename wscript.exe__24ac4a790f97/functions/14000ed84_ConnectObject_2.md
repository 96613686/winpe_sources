# ConnectObject_2

- ea: `0x14000ed84`
- end: `0x14000ee75`
- name: `ConnectObject_2`
- size: `241`
- prototype: `__int64 __fastcall(struct IDispatch *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000e9f4`
- `0x14000eb48`
- `0x14000ec44`

## callees

- `0x140001008`
- `0x14000ed84`
- `0x14000faf4`
- `0x140010510`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall ConnectObject_2(struct IDispatch *a1, __int64 a2, unsigned __int16 *a3)
{
  _QWORD *v6; // rbx
  int SourceFromClass; // eax
  struct ITypeInfo *v8; // rsi
  int v9; // edi
  struct ITypeInfo *v11; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  v6 = operator new(0x50u);
  if ( v6 )
  {
    v6[1] = 0;
    *v6 = &CConnectionSink::`vftable';
    v6[2] = 0;
    v6[3] = 0;
    v6[4] = 0;
    *((_DWORD *)v6 + 10) = -1;
    v6[6] = 0;
    *((_DWORD *)v6 + 14) = 1;
    SourceFromClass = GetSourceFromClass(a2, &v11);
    v8 = v11;
    v9 = SourceFromClass;
    if ( SourceFromClass >= 0 )
    {
      v9 = CConnectionSink::Connect((CConnectionSink *)v6, a1, v11, a3);
      if ( v9 >= 0 )
      {
        v6 = 0;
        v9 = 0;
      }
    }
    if ( v8 )
      ((void (__fastcall *)(struct ITypeInfo *))v8->lpVtbl->Release)(v8);
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000ed84  mov     [rsp+arg_0], rbx
0x14000ed89  mov     [rsp+arg_8], rbp
0x14000ed8e  push    rsi
0x14000ed8f  push    rdi
0x14000ed90  push    r14
0x14000ed92  sub     rsp, 20h
0x14000ed96  mov     r14, rcx
0x14000ed99  mov     [rsp+38h+arg_18], 0
0x14000eda2  mov     ecx, 50h ; 'P'; Size
0x14000eda7  mov     rbp, r8
0x14000edaa  mov     rdi, rdx
0x14000edad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000edb2  mov     rbx, rax
0x14000edb5  test    rax, rax
0x14000edb8  jz      loc_14000EE5B
0x14000edbe  lea     rax, ??_7CConnectionSink@@6B@; const CConnectionSink::`vftable'
0x14000edc5  mov     qword ptr [rbx+8], 0
0x14000edcd  lea     rdx, [rsp+38h+arg_18]
0x14000edd2  mov     [rbx], rax
0x14000edd5  mov     rcx, rdi
0x14000edd8  mov     qword ptr [rbx+10h], 0
0x14000ede0  mov     qword ptr [rbx+18h], 0
0x14000ede8  mov     qword ptr [rbx+20h], 0
0x14000edf0  mov     dword ptr [rbx+28h], 0FFFFFFFFh
0x14000edf7  mov     qword ptr [rbx+30h], 0
0x14000edff  mov     dword ptr [rbx+38h], 1
0x14000ee06  call    GetSourceFromClass
0x14000ee0b  mov     rsi, [rsp+38h+arg_18]
0x14000ee10  mov     edi, eax
0x14000ee12  test    eax, eax
0x14000ee14  js      short loc_14000EE31
0x14000ee16  mov     r9, rbp; unsigned __int16 *
0x14000ee19  mov     r8, rsi; struct ITypeInfo *
0x14000ee1c  mov     rdx, r14; struct IDispatch *
0x14000ee1f  mov     rcx, rbx; this
0x14000ee22  call    ?Connect@CConnectionSink@@QEAAJPEAUIDispatch@@PEAUITypeInfo@@PEAG@Z; CConnectionSink::Connect(IDispatch *,ITypeInfo *,ushort *)
0x14000ee27  mov     edi, eax
0x14000ee29  test    eax, eax
0x14000ee2b  js      short loc_14000EE31
0x14000ee2d  xor     ebx, ebx
0x14000ee2f  xor     edi, edi
0x14000ee31  test    rsi, rsi
0x14000ee34  jz      short loc_14000EE45
0x14000ee36  mov     rax, [rsi]
0x14000ee39  mov     rcx, rsi
0x14000ee3c  mov     rax, [rax+10h]
0x14000ee40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee45  test    rbx, rbx
0x14000ee48  jz      short loc_14000EE60
0x14000ee4a  mov     rax, [rbx]
0x14000ee4d  mov     rcx, rbx
0x14000ee50  mov     rax, [rax+10h]
0x14000ee54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee59  jmp     short loc_14000EE60
0x14000ee5b  mov     edi, 8007000Eh
0x14000ee60  mov     rbx, [rsp+38h+arg_0]
0x14000ee65  mov     eax, edi
0x14000ee67  mov     rbp, [rsp+38h+arg_8]
0x14000ee6c  add     rsp, 20h
0x14000ee70  pop     r14
0x14000ee72  pop     rdi
0x14000ee73  pop     rsi
0x14000ee74  retn
```
