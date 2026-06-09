# __DestructExceptionObject

- ea: `0x140002bc0`
- end: `0x140002c33`
- name: `__DestructExceptionObject`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002d48`
- `0x140003624`
- `0x140004670`

## callees

- `0x140002bc0`
- `0x140002c3c`
- `0x140003008`
- `0x1400056fa`
- `0x1400059e0`

## pseudocode

```c
void __fastcall _DestructExceptionObject(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx

  if ( a1 )
  {
    if ( *(_DWORD *)a1 == -529697949 && *(_DWORD *)(a1 + 24) == 4 )
    {
      v1 = *(_DWORD *)(a1 + 32);
      if ( v1 == 429065504 || (unsigned int)(v1 - 429065505) <= 1 )
      {
        v2 = *(_QWORD *)(a1 + 48);
        if ( v2 )
        {
          v3 = *(int *)(v2 + 4);
          if ( (_DWORD)v3 )
          {
            ((void (__fastcall *)(_QWORD))(*(_QWORD *)(a1 + 56) + v3))(*(_QWORD *)(a1 + 40));
          }
          else if ( (*(_BYTE *)v2 & 0x10) != 0 )
          {
            v4 = **(_QWORD **)(a1 + 40);
            if ( v4 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140002bc0  test    rcx, rcx
0x140002bc3  jz      short locret_140002C32
0x140002bc5  mov     [rsp+arg_8], dl
0x140002bc9  sub     rsp, 48h
0x140002bcd  cmp     dword ptr [rcx], 0E06D7363h
0x140002bd3  jnz     short loc_140002C2E
0x140002bd5  cmp     dword ptr [rcx+18h], 4
0x140002bd9  jnz     short loc_140002C2E
0x140002bdb  mov     eax, [rcx+20h]
0x140002bde  cmp     eax, 19930520h
0x140002be3  jz      short loc_140002BEF
0x140002be5  add     eax, 0E66CFADFh
0x140002bea  cmp     eax, 1
0x140002bed  ja      short loc_140002C2E
0x140002bef  mov     rax, [rcx+30h]
0x140002bf3  test    rax, rax
0x140002bf6  jz      short loc_140002C2E
0x140002bf8  movsxd  rdx, dword ptr [rax+4]
0x140002bfc  test    edx, edx
0x140002bfe  jz      short loc_140002C11
0x140002c00  add     rdx, [rcx+38h]; void *
0x140002c04  mov     rcx, [rcx+28h]; void *
0x140002c08  call    ?_CallMemberFunction0@@YAXQEAX0@Z; _CallMemberFunction0(void * const,void * const)
0x140002c0d  jmp     short loc_140002C2E
0x140002c0f  jmp     short loc_140002C2E
0x140002c11  test    byte ptr [rax], 10h
0x140002c14  jz      short loc_140002C2E
0x140002c16  mov     rax, [rcx+28h]
0x140002c1a  mov     rcx, [rax]
0x140002c1d  test    rcx, rcx
0x140002c20  jz      short loc_140002C2E
0x140002c22  mov     rax, [rcx]
0x140002c25  mov     rax, [rax+10h]
0x140002c29  call    _guard_dispatch_icall
0x140002c2e  add     rsp, 48h
0x140002c32  retn
0x1400065a2  push    rbx
0x1400065a4  push    rbp
0x1400065a5  sub     rsp, 28h
0x1400065a9  mov     rbp, rdx
0x1400065ac  mov     [rbp+30h], rcx
0x1400065b0  cmp     byte ptr [rbp+58h], 0
0x1400065b4  jz      short loc_140006622
0x1400065b6  mov     rax, [rbp+30h]
0x1400065ba  mov     rcx, [rax]
0x1400065bd  mov     [rbp+28h], rcx
0x1400065c1  mov     rax, [rbp+28h]
0x1400065c5  cmp     dword ptr [rax], 0E06D7363h
0x1400065cb  jnz     short loc_140006622
0x1400065cd  mov     rax, [rbp+28h]
0x1400065d1  cmp     dword ptr [rax+18h], 4
0x1400065d5  jnz     short loc_140006622
0x1400065d7  mov     rax, [rbp+28h]
0x1400065db  cmp     dword ptr [rax+20h], 19930520h
0x1400065e2  jz      short loc_1400065FE
0x1400065e4  mov     rax, [rbp+28h]
0x1400065e8  cmp     dword ptr [rax+20h], 19930521h
0x1400065ef  jz      short loc_1400065FE
0x1400065f1  mov     rax, [rbp+28h]
0x1400065f5  cmp     dword ptr [rax+20h], 19930522h
0x1400065fc  jnz     short loc_140006622
0x1400065fe  call    __vcrt_getptd
0x140006603  mov     rcx, [rbp+28h]
0x140006607  mov     [rax+20h], rcx
0x14000660b  mov     rax, [rbp+30h]
0x14000660f  mov     rbx, [rax+8]
0x140006613  call    __vcrt_getptd
0x140006618  mov     [rax+28h], rbx
0x14000661c  call    _o_terminate_0
0x140006621  nop
0x140006622  mov     dword ptr [rbp+20h], 0
0x140006629  mov     eax, [rbp+20h]
0x14000662c  add     rsp, 28h
0x140006630  pop     rbp
0x140006631  pop     rbx
0x140006632  retn
```
