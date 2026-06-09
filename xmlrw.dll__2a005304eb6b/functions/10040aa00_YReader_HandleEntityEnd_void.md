# YReader::HandleEntityEnd(void *)

- ea: `0x10040aa00`
- end: `0x10040ab9e`
- name: `?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z`
- size: `414`
- prototype: `struct DeclEntity *__fastcall(YReader *__hidden this, void *)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100404de0`
- `0x100407620`
- `0x100407ec0`
- `0x10040a020`
- `0x10040a270`
- `0x10040a4c0`

## callees

- `0x100401780`
- `0x10040aa00`
- `0x100439df0`

## pseudocode

```c
struct DeclEntity *__fastcall YReader::HandleEntityEnd(YReader *this, void *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rsi
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  __int64 v10; // rdx
  void (__fastcall ***v11)(_QWORD, __int64); // rcx

  v4 = *(_QWORD *)(*((_QWORD *)this + 58) + 8LL * (unsigned int)(*((_DWORD *)this + 118) - 1));
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
  v6 = v5;
  if ( *((_DWORD *)this + 118) == 1 )
  {
    MXRRaiseException(-1072894463);
    __debugbreak();
  }
  if ( *(_BYTE *)(v5 + 128) )
    --*((_DWORD *)this + 464);
  if ( !*(_BYTE *)(v5 + 132) )
  {
    if ( *(void **)(v5 + 136) != a2 )
    {
      MXRRaiseException(-1072894394);
      JUMPOUT(0x10040AB9DLL);
    }
    *(_QWORD *)(v5 + 136) = 0;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 40LL))(*((_QWORD *)this + 13));
  --*((_DWORD *)this + 20);
  v8 = v7;
  v9 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 9) + 8LL * *((unsigned int *)this + 20));
  if ( v9 )
    (**v9)(v9, 1);
  if ( *((_DWORD *)this + 20) )
  {
    v10 = *(_QWORD *)(*((_QWORD *)this + 9) + 8LL * (unsigned int)(*((_DWORD *)this + 20) - 1));
    *((_QWORD *)this + 13) = v10;
    *(_QWORD *)(v10 + 56) = *(_QWORD *)(v10 + 48);
    *(_DWORD *)(v10 + 88) = 1;
  }
  else
  {
    *((_QWORD *)this + 13) = 0;
  }
  if ( *((void (__fastcall **)(Scanner *__hidden))this + 27) == Scanner::ScanEntityValue )
  {
    *((_WORD *)this + 152) = *(_WORD *)(*((_QWORD *)this + 31) + 2LL * (unsigned int)--*((_DWORD *)this + 64));
  }
  else if ( *(_BYTE *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 40LL))(v8) + 131) )
  {
    *((_QWORD *)this + 27) = *(_QWORD *)(*((_QWORD *)this + 17) + 8LL * (unsigned int)(--*((_DWORD *)this + 36) - 1));
  }
  v11 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 58) + 8LL
                                                                          * (unsigned int)--*((_DWORD *)this + 118));
  if ( v11 )
    (**v11)(v11, 1);
  return (struct DeclEntity *)v6;
}

```

## disassembly

```asm
0x10040aa00  mov     [rsp+arg_0], rbx
0x10040aa05  mov     [rsp+arg_8], rsi
0x10040aa0a  push    rdi
0x10040aa0b  sub     rsp, 20h
0x10040aa0f  mov     r8d, [rcx+1D8h]
0x10040aa16  mov     rbx, rcx
0x10040aa19  mov     rax, [rcx+1D0h]
0x10040aa20  dec     r8d
0x10040aa23  mov     rsi, rdx
0x10040aa26  mov     rcx, [rax+r8*8]
0x10040aa2a  mov     rax, [rcx]
0x10040aa2d  mov     rax, [rax+28h]
0x10040aa31  call    cs:__guard_dispatch_icall_fptr
0x10040aa37  cmp     dword ptr [rbx+1D8h], 1
0x10040aa3e  mov     rdi, rax
0x10040aa41  jz      loc_10040AB88
0x10040aa47  cmp     byte ptr [rax+80h], 0
0x10040aa4e  jz      short loc_10040AA56
0x10040aa50  dec     dword ptr [rbx+740h]
0x10040aa56  cmp     byte ptr [rax+84h], 0
0x10040aa5d  jnz     short loc_10040AA77
0x10040aa5f  cmp     [rax+88h], rsi
0x10040aa66  jnz     loc_10040AB93
0x10040aa6c  mov     qword ptr [rax+88h], 0
0x10040aa77  mov     rcx, [rbx+68h]
0x10040aa7b  mov     rax, [rcx]
0x10040aa7e  mov     rax, [rax+28h]
0x10040aa82  call    cs:__guard_dispatch_icall_fptr
0x10040aa88  dec     dword ptr [rbx+50h]
0x10040aa8b  mov     rsi, rax
0x10040aa8e  mov     edx, [rbx+50h]
0x10040aa91  mov     rcx, [rbx+48h]
0x10040aa95  mov     rcx, [rcx+rdx*8]
0x10040aa99  test    rcx, rcx
0x10040aa9c  jz      short loc_10040AAAF
0x10040aa9e  mov     rdx, [rcx]
0x10040aaa1  mov     rax, [rdx]
0x10040aaa4  mov     edx, 1
0x10040aaa9  call    cs:__guard_dispatch_icall_fptr
0x10040aaaf  cmp     dword ptr [rbx+50h], 0
0x10040aab3  jz      short loc_10040AAD7
0x10040aab5  mov     ecx, [rbx+50h]
0x10040aab8  mov     rax, [rbx+48h]
0x10040aabc  dec     ecx
0x10040aabe  mov     rdx, [rax+rcx*8]
0x10040aac2  mov     [rbx+68h], rdx
0x10040aac6  mov     rax, [rdx+30h]
0x10040aaca  mov     [rdx+38h], rax
0x10040aace  mov     dword ptr [rdx+58h], 1
0x10040aad5  jmp     short loc_10040AADF
0x10040aad7  mov     qword ptr [rbx+68h], 0
0x10040aadf  lea     rax, ?ScanEntityValue@Scanner@@AEAAXXZ; Scanner::ScanEntityValue(void)
0x10040aae6  cmp     [rbx+0D8h], rax
0x10040aaed  jnz     short loc_10040AB0F
0x10040aaef  dec     dword ptr [rbx+100h]
0x10040aaf5  mov     ecx, [rbx+100h]
0x10040aafb  mov     rax, [rbx+0F8h]
0x10040ab02  movzx   ecx, word ptr [rax+rcx*2]
0x10040ab06  mov     [rbx+130h], cx
0x10040ab0d  jmp     short loc_10040AB48
0x10040ab0f  mov     rax, [rsi]
0x10040ab12  mov     rcx, rsi
0x10040ab15  mov     rax, [rax+28h]
0x10040ab19  call    cs:__guard_dispatch_icall_fptr
0x10040ab1f  cmp     byte ptr [rax+83h], 0
0x10040ab26  jz      short loc_10040AB48
0x10040ab28  dec     dword ptr [rbx+90h]
0x10040ab2e  mov     ecx, [rbx+90h]
0x10040ab34  mov     rax, [rbx+88h]
0x10040ab3b  dec     ecx
0x10040ab3d  mov     rcx, [rax+rcx*8]
0x10040ab41  mov     [rbx+0D8h], rcx
0x10040ab48  dec     dword ptr [rbx+1D8h]
0x10040ab4e  mov     ecx, [rbx+1D8h]
0x10040ab54  mov     rax, [rbx+1D0h]
0x10040ab5b  mov     rcx, [rax+rcx*8]
0x10040ab5f  test    rcx, rcx
0x10040ab62  jz      short loc_10040AB75
0x10040ab64  mov     rax, [rcx]
0x10040ab67  mov     edx, 1
0x10040ab6c  mov     rax, [rax]
0x10040ab6f  call    cs:__guard_dispatch_icall_fptr
0x10040ab75  mov     rbx, [rsp+28h+arg_0]
0x10040ab7a  mov     rax, rdi
0x10040ab7d  mov     rsi, [rsp+28h+arg_8]
0x10040ab82  add     rsp, 20h
0x10040ab86  pop     rdi
0x10040ab87  retn
0x10040ab88  mov     ecx, 0C00CEE01h; int
0x10040ab8d  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040ab92  int     3; Trap to Debugger
0x10040ab93  mov     ecx, 0C00CEE46h; int
0x10040ab98  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
