# WEBHOST_PROTOCOL_MANAGER::GetPmInterface(PM_INTERFACE_ID_ENUM,void * *)

- ea: `0x180002080`
- end: `0x18000211c`
- name: `?GetPmInterface@WEBHOST_PROTOCOL_MANAGER@@UEAAJW4PM_INTERFACE_ID_ENUM@@PEAPEAX@Z`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002080`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::GetPmInterface(void (__fastcall ***a1)(_QWORD), int a2, __int64 *a3)
{
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  unsigned __int64 v10; // rcx

  v5 = a2 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( v8 != 1 )
            return 2147942487LL;
          (**a1)(a1);
          v10 = (unsigned __int64)(a1 + 5);
        }
        else
        {
          (**a1)(a1);
          v10 = (unsigned __int64)(a1 + 4);
        }
      }
      else
      {
        (**a1)(a1);
        v10 = (unsigned __int64)(a1 + 1);
      }
    }
    else
    {
      (**a1)(a1);
      v10 = (unsigned __int64)(a1 + 2);
    }
  }
  else
  {
    (**a1)(a1);
    v10 = (unsigned __int64)(a1 + 3);
  }
  *a3 = v10 & -(__int64)(a1 != 0);
  return 0;
}

```

## disassembly

```asm
0x180002080  mov     [rsp+arg_0], rbx
0x180002085  push    rdi
0x180002086  sub     rsp, 20h
0x18000208a  mov     rdi, r8
0x18000208d  mov     rbx, rcx
0x180002090  sub     edx, 1
0x180002093  jz      short loc_1800020F4
0x180002095  sub     edx, 1
0x180002098  jz      short loc_1800020E3
0x18000209a  sub     edx, 1
0x18000209d  jz      short loc_1800020D2
0x18000209f  sub     edx, 1
0x1800020a2  jz      short loc_1800020C1
0x1800020a4  cmp     edx, 1
0x1800020a7  jz      short loc_1800020B0
0x1800020a9  mov     eax, 80070057h
0x1800020ae  jmp     short loc_180002111
0x1800020b0  mov     rax, [rcx]
0x1800020b3  mov     rax, [rax]
0x1800020b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020bb  lea     rcx, [rbx+28h]
0x1800020bf  jmp     short loc_180002103
0x1800020c1  mov     rax, [rcx]
0x1800020c4  mov     rax, [rax]
0x1800020c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020cc  lea     rcx, [rbx+20h]
0x1800020d0  jmp     short loc_180002103
0x1800020d2  mov     rax, [rcx]
0x1800020d5  mov     rax, [rax]
0x1800020d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020dd  lea     rcx, [rbx+8]
0x1800020e1  jmp     short loc_180002103
0x1800020e3  mov     rax, [rcx]
0x1800020e6  mov     rax, [rax]
0x1800020e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ee  lea     rcx, [rbx+10h]
0x1800020f2  jmp     short loc_180002103
0x1800020f4  mov     rax, [rcx]
0x1800020f7  mov     rax, [rax]
0x1800020fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ff  lea     rcx, [rbx+18h]
0x180002103  neg     rbx
0x180002106  sbb     rax, rax
0x180002109  and     rax, rcx
0x18000210c  mov     [rdi], rax
0x18000210f  xor     eax, eax
0x180002111  mov     rbx, [rsp+28h+arg_0]
0x180002116  add     rsp, 20h
0x18000211a  pop     rdi
0x18000211b  retn
```
