# PMH_SUPPORT_FCNS::Shutdown(void)

- ea: `0x180002ec0`
- end: `0x180002f71`
- name: `?Shutdown@PMH_SUPPORT_FCNS@@QEAAXXZ`
- size: `177`
- prototype: `void __fastcall(PMH_SUPPORT_FCNS *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f80`
- `0x1800037e8`

## callees

- `0x180002ec0`
- `0x180005010`

## pseudocode

```c
void __fastcall PMH_SUPPORT_FCNS::Shutdown(PMH_SUPPORT_FCNS *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = *((_QWORD *)this + 4);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 4) = 0;
  }
  v3 = *((_QWORD *)this + 5);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 5) = 0;
  }
  v4 = *((_QWORD *)this + 6);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    *((_QWORD *)this + 6) = 0;
  }
  if ( *((_QWORD *)this + 7) )
    *((_QWORD *)this + 7) = 0;
  v5 = *((_QWORD *)this + 22);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    *((_QWORD *)this + 22) = 0;
  }
  if ( *((_QWORD *)this + 3) )
    *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 46) = 1;
}

```

## disassembly

```asm
0x180002ec0  push    rbx
0x180002ec2  sub     rsp, 20h
0x180002ec6  mov     rbx, rcx
0x180002ec9  mov     rcx, [rcx+20h]
0x180002ecd  test    rcx, rcx
0x180002ed0  jz      short loc_180002EE6
0x180002ed2  mov     rax, [rcx]
0x180002ed5  mov     rax, [rax+10h]
0x180002ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ede  mov     qword ptr [rbx+20h], 0
0x180002ee6  mov     rcx, [rbx+28h]
0x180002eea  test    rcx, rcx
0x180002eed  jz      short loc_180002F03
0x180002eef  mov     rax, [rcx]
0x180002ef2  mov     rax, [rax+10h]
0x180002ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002efb  mov     qword ptr [rbx+28h], 0
0x180002f03  mov     rcx, [rbx+30h]
0x180002f07  test    rcx, rcx
0x180002f0a  jz      short loc_180002F20
0x180002f0c  mov     rax, [rcx]
0x180002f0f  mov     rax, [rax+8]
0x180002f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f18  mov     qword ptr [rbx+30h], 0
0x180002f20  cmp     qword ptr [rbx+38h], 0
0x180002f25  jz      short loc_180002F2F
0x180002f27  mov     qword ptr [rbx+38h], 0
0x180002f2f  mov     rcx, [rbx+0B0h]
0x180002f36  test    rcx, rcx
0x180002f39  jz      short loc_180002F52
0x180002f3b  mov     rax, [rcx]
0x180002f3e  mov     rax, [rax+8]
0x180002f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f47  mov     qword ptr [rbx+0B0h], 0
0x180002f52  cmp     qword ptr [rbx+18h], 0
0x180002f57  jz      short loc_180002F61
0x180002f59  mov     qword ptr [rbx+18h], 0
0x180002f61  mov     dword ptr [rbx+0B8h], 1
0x180002f6b  add     rsp, 20h
0x180002f6f  pop     rbx
0x180002f70  retn
```
