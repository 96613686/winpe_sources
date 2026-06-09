# CFSSecurity::GetSecondarySecurity(_SECURITY_OBJECT * *,ulong *)

- ea: `0x180005f40`
- end: `0x180005fcc`
- name: `?GetSecondarySecurity@CFSSecurity@@UEAAJPEAPEAU_SECURITY_OBJECT@@PEAK@Z`
- size: `140`
- prototype: `__int64 __fastcall(CFSSecurity *__hidden this, struct _SECURITY_OBJECT **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005f40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f6e`

## pseudocode

```c
__int64 __fastcall CFSSecurity::GetSecondarySecurity(CFSSecurity *this, struct _SECURITY_OBJECT **a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  _BYTE *v7; // rax

  if ( a2 && a3 )
  {
    v6 = 0;
    if ( *((_QWORD *)this + 74) )
    {
      v7 = LocalAlloc(0x40u, 0x30u);
      if ( v7 )
      {
        v7[40] = 1;
        *((_DWORD *)v7 + 9) = 2;
        *((_DWORD *)v7 + 4) = 272;
        *((_QWORD *)v7 + 1) = *((_QWORD *)this + 74);
        *(_QWORD *)v7 = (char *)this + 386;
        *a2 = (struct _SECURITY_OBJECT *)v7;
        *a3 = 1;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      *a2 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180005f40  push    rbx
0x180005f42  push    rsi
0x180005f43  push    rdi
0x180005f44  push    r14
0x180005f46  sub     rsp, 28h
0x180005f4a  mov     r14, r8
0x180005f4d  mov     rdi, rdx
0x180005f50  mov     rsi, rcx
0x180005f53  test    rdx, rdx
0x180005f56  jz      short loc_180005FBB
0x180005f58  test    r8, r8
0x180005f5b  jz      short loc_180005FBB
0x180005f5d  xor     ebx, ebx
0x180005f5f  cmp     [rcx+250h], rbx
0x180005f66  jz      short loc_180005FB6
0x180005f68  lea     edx, [rbx+30h]; uBytes
0x180005f6b  lea     ecx, [rbx+40h]; uFlags
0x180005f6e  call    cs:__imp_LocalAlloc
0x180005f74  mov     rcx, rax
0x180005f77  test    rax, rax
0x180005f7a  jnz     short loc_180005F83
0x180005f7c  mov     ebx, 8007000Eh
0x180005f81  jmp     short loc_180005FC0
0x180005f83  mov     byte ptr [rax+28h], 1
0x180005f87  mov     dword ptr [rax+24h], 2
0x180005f8e  mov     dword ptr [rax+10h], 110h
0x180005f95  mov     rax, [rsi+250h]
0x180005f9c  mov     [rcx+8], rax
0x180005fa0  lea     rax, [rsi+182h]
0x180005fa7  mov     [rcx], rax
0x180005faa  mov     [rdi], rcx
0x180005fad  mov     dword ptr [r14], 1
0x180005fb4  jmp     short loc_180005FC0
0x180005fb6  mov     [rdx], rbx
0x180005fb9  jmp     short loc_180005FC0
0x180005fbb  mov     ebx, 80070057h
0x180005fc0  mov     eax, ebx
0x180005fc2  add     rsp, 28h
0x180005fc6  pop     r14
0x180005fc8  pop     rdi
0x180005fc9  pop     rsi
0x180005fca  pop     rbx
0x180005fcb  retn
```
