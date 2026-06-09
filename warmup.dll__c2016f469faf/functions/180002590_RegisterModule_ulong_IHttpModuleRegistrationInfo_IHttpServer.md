# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002590`
- end: `0x180002686`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001008`
- `0x180002590`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  int v7; // edi
  _QWORD *v8; // rax
  _QWORD *v9; // rsi
  __int64 result; // rax

  v5 = operator new(0x10u);
  v6 = v5;
  if ( v5 )
  {
    *v5 = &CModuleFactory::`vftable';
    v5[1] = &CIISModule::`vftable';
    v7 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
           a2,
           v5,
           134217729,
           0);
    if ( v7 >= 0 )
    {
      v8 = operator new(8u);
      v9 = v8;
      if ( v8 )
      {
        *v8 = &CIISGlobalModule::`vftable';
        v7 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
               a2,
               v8,
               66048);
        if ( v7 >= 0 )
        {
          g_ModuleID = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
          result = 0;
          g_pServer = a3;
          return result;
        }
        goto LABEL_8;
      }
      v7 = -2147024888;
    }
    v9 = 0;
LABEL_8:
    (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
    if ( v9 )
      (*(void (__fastcall **)(_QWORD *))(*v9 + 104LL))(v9);
    return (unsigned int)v7;
  }
  return (unsigned int)-2147024888;
}

```

## disassembly

```asm
0x180002590  push    rbx
0x180002592  push    rbp
0x180002593  push    rsi
0x180002594  push    rdi
0x180002595  push    r14
0x180002597  sub     rsp, 30h
0x18000259b  mov     ecx, 10h; Size
0x1800025a0  mov     rbp, r8
0x1800025a3  mov     r14, rdx
0x1800025a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800025ab  mov     rbx, rax
0x1800025ae  test    rax, rax
0x1800025b1  jz      loc_180002674
0x1800025b7  lea     rax, ??_7CModuleFactory@@6B@; const CModuleFactory::`vftable'
0x1800025be  xor     r9d, r9d
0x1800025c1  mov     [rbx], rax
0x1800025c4  mov     r8d, 8000001h
0x1800025ca  lea     rax, ??_7CIISModule@@6B@; const CIISModule::`vftable'
0x1800025d1  mov     rdx, rbx
0x1800025d4  mov     [rbx+8], rax
0x1800025d8  mov     rcx, r14
0x1800025db  mov     rax, [r14]
0x1800025de  mov     rax, [rax+10h]
0x1800025e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e7  mov     edi, eax
0x1800025e9  test    eax, eax
0x1800025eb  js      short loc_18000264D
0x1800025ed  mov     ecx, 8; Size
0x1800025f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800025f7  mov     rsi, rax
0x1800025fa  test    rax, rax
0x1800025fd  jz      short loc_180002648
0x1800025ff  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x180002606  mov     r8d, 10200h
0x18000260c  mov     [rsi], rax
0x18000260f  mov     rdx, rsi
0x180002612  mov     rax, [r14]
0x180002615  mov     rcx, r14
0x180002618  mov     rax, [rax+18h]
0x18000261c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002621  mov     edi, eax
0x180002623  test    eax, eax
0x180002625  js      short loc_18000264F
0x180002627  mov     rax, [r14]
0x18000262a  mov     rcx, r14
0x18000262d  mov     rax, [rax+8]
0x180002631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002636  mov     cs:?g_ModuleID@@3PEAXEA, rax; void * g_ModuleID
0x18000263d  xor     eax, eax
0x18000263f  mov     cs:?g_pServer@@3PEAVIHttpServer@@EA, rbp; IHttpServer * g_pServer
0x180002646  jmp     short loc_18000267B
0x180002648  mov     edi, 80070008h
0x18000264d  xor     esi, esi
0x18000264f  mov     rax, [rbx]
0x180002652  mov     rcx, rbx
0x180002655  mov     rax, [rax+8]
0x180002659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000265e  test    rsi, rsi
0x180002661  jz      short loc_180002679
0x180002663  mov     rax, [rsi]
0x180002666  mov     rcx, rsi
0x180002669  mov     rax, [rax+68h]
0x18000266d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002672  jmp     short loc_180002679
0x180002674  mov     edi, 80070008h
0x180002679  mov     eax, edi
0x18000267b  add     rsp, 30h
0x18000267f  pop     r14
0x180002681  pop     rdi
0x180002682  pop     rsi
0x180002683  pop     rbp
0x180002684  pop     rbx
0x180002685  retn
```
