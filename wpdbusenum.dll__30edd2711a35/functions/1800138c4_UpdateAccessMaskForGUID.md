# UpdateAccessMaskForGUID

- ea: `0x1800138c4`
- end: `0x180013963`
- name: `UpdateAccessMaskForGUID`
- size: `159`
- prototype: `char *__fastcall(char **, _QWORD *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180004f10`
- `0x180005420`

## callees

- `0x1800138c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001390b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001390b`

## pseudocode

```c
char *__fastcall UpdateAccessMaskForGUID(char **a1, _QWORD *a2, int a3)
{
  char *result; // rax
  __int64 v7; // r9
  __int128 v8; // xmm0

  for ( result = *a1; result; result = *(char **)result )
  {
    v7 = *(_QWORD *)(result + 28) - *a2;
    if ( !v7 )
      v7 = *(_QWORD *)(result + 36) - a2[1];
    if ( !v7 )
    {
      *((_DWORD *)result + 11) |= a3;
      return result;
    }
  }
  result = (char *)LocalAlloc(0x40u, 0x40u);
  if ( result )
  {
    v8 = *(_OWORD *)a2;
    *((_QWORD *)result + 1) = 0;
    *((_DWORD *)result + 12) = 1;
    *((_DWORD *)result + 15) = 1;
    *(_QWORD *)result = *a1;
    *(_OWORD *)(result + 28) = v8;
    *((_QWORD *)result + 2) = 0;
    *((_DWORD *)result + 6) = 0;
    *((_DWORD *)result + 11) = a3;
    *((_DWORD *)result + 14) = 0;
    *a1 = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800138c4  mov     [rsp+arg_0], rbx
0x1800138c9  mov     [rsp+arg_8], rsi
0x1800138ce  push    rdi
0x1800138cf  sub     rsp, 20h
0x1800138d3  mov     rax, [rcx]
0x1800138d6  mov     edi, r8d
0x1800138d9  mov     rbx, rdx
0x1800138dc  mov     rsi, rcx
0x1800138df  test    rax, rax
0x1800138e2  jz      short loc_180013904
0x1800138e4  mov     r9, [rax+1Ch]
0x1800138e8  sub     r9, [rdx]
0x1800138eb  jnz     short loc_1800138F5
0x1800138ed  mov     r9, [rax+24h]
0x1800138f1  sub     r9, [rdx+8]
0x1800138f5  test    r9, r9
0x1800138f8  jz      short loc_1800138FF
0x1800138fa  mov     rax, [rax]
0x1800138fd  jmp     short loc_1800138DF
0x1800138ff  or      [rax+2Ch], edi
0x180013902  jmp     short loc_180013953
0x180013904  mov     ecx, 40h ; '@'; uFlags
0x180013909  mov     edx, ecx; uBytes
0x18001390b  call    cs:__imp_LocalAlloc
0x180013911  test    rax, rax
0x180013914  jz      short loc_180013953
0x180013916  movups  xmm0, xmmword ptr [rbx]
0x180013919  mov     ecx, 1
0x18001391e  mov     qword ptr [rax+8], 0
0x180013926  mov     [rax+30h], ecx
0x180013929  mov     [rax+3Ch], ecx
0x18001392c  mov     rcx, [rsi]
0x18001392f  mov     [rax], rcx
0x180013932  movdqu  xmmword ptr [rax+1Ch], xmm0
0x180013937  mov     qword ptr [rax+10h], 0
0x18001393f  mov     dword ptr [rax+18h], 0
0x180013946  mov     [rax+2Ch], edi
0x180013949  mov     dword ptr [rax+38h], 0
0x180013950  mov     [rsi], rax
0x180013953  mov     rbx, [rsp+28h+arg_0]
0x180013958  mov     rsi, [rsp+28h+arg_8]
0x18001395d  add     rsp, 20h
0x180013961  pop     rdi
0x180013962  retn
```
