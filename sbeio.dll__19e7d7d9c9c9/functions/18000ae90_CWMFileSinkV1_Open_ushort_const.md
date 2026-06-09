# CWMFileSinkV1::Open(ushort const *)

- ea: `0x18000ae90`
- end: `0x18000af8e`
- name: `?Open@CWMFileSinkV1@@UEAAJPEBG@Z`
- size: `254`
- prototype: `int(CWMFileSinkV1 *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005060`
- `0x180007e38`
- `0x18000ae90`
- `0x18002b010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000af60`
- `KERNEL32!LeaveCriticalSection` at `0x18000af60`
- `KERNEL32!EnterCriticalSection` at `0x18000aef3`
- `KERNEL32!EnterCriticalSection` at `0x18000aef3`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::Open(CWMFileSinkV1 *this, const unsigned __int16 *a2)
{
  __int64 v3; // r11
  unsigned int v4; // ebp
  unsigned int v5; // esi
  _QWORD *v6; // rax

  if ( !a2 || (int)StringCchLengthW(a2, 0x104u, 0) < 0 )
    return 2147942487LL;
  v4 = (*(__int64 (__fastcall **)(CWMFileSinkV1 *, __int64))(*(_QWORD *)this + 216LL))(this, v3);
  if ( *((_DWORD *)this + 2308) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
    if ( *((_DWORD *)this + 2306) )
    {
      v5 = 0;
      do
      {
        v6 = (_QWORD *)CTPtrArray<unsigned char,20>::operator[]((char *)this + 9008, v5);
        if ( v6 )
        {
          if ( *v6 )
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v6 + 24LL))(*v6, 1, v4);
        }
        ++v5;
      }
      while ( v5 < *((_DWORD *)this + 2306) );
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  }
  else
  {
    *((_DWORD *)this + 2308) = 1;
  }
  return v4;
}

```

## disassembly

```asm
0x18000ae90  mov     [rsp+arg_0], rbx
0x18000ae95  mov     [rsp+arg_10], rbp
0x18000ae9a  push    rsi
0x18000ae9b  push    rdi
0x18000ae9c  push    r14
0x18000ae9e  sub     rsp, 40h
0x18000aea2  mov     r11, rdx
0x18000aea5  mov     rdi, rcx
0x18000aea8  test    rdx, rdx
0x18000aeab  jz      loc_18000AF76
0x18000aeb1  xor     r8d, r8d; unsigned __int64 *
0x18000aeb4  mov     edx, 104h; unsigned __int64
0x18000aeb9  mov     rcx, r11; unsigned __int16 *
0x18000aebc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000aec1  test    eax, eax
0x18000aec3  js      loc_18000AF76
0x18000aec9  mov     rax, [rdi]
0x18000aecc  mov     rdx, r11
0x18000aecf  mov     rcx, rdi
0x18000aed2  mov     rax, [rax+0D8h]
0x18000aed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aede  cmp     dword ptr [rdi+2410h], 0
0x18000aee5  mov     ebp, eax
0x18000aee7  jz      short loc_18000AF68
0x18000aee9  lea     rbx, [rdi+90h]
0x18000aef0  mov     rcx, rbx; lpCriticalSection
0x18000aef3  call    cs:__imp_EnterCriticalSection
0x18000aef9  cmp     dword ptr [rdi+2408h], 0
0x18000af00  jbe     short loc_18000AF5D
0x18000af02  mov     [rsp+58h+arg_8], 0
0x18000af0a  xor     esi, esi
0x18000af0c  mov     edx, esi
0x18000af0e  lea     rcx, [rdi+2330h]
0x18000af15  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000af1a  mov     r8, rax
0x18000af1d  test    rax, rax
0x18000af20  jz      short loc_18000AF53
0x18000af22  mov     rcx, [rax]
0x18000af25  test    rcx, rcx
0x18000af28  jz      short loc_18000AF53
0x18000af2a  mov     rdx, [rcx]
0x18000af2d  xor     r9d, r9d
0x18000af30  mov     rax, [rdx+18h]
0x18000af34  mov     rdx, [r8+8]
0x18000af38  mov     r8d, ebp
0x18000af3b  mov     [rsp+58h+var_30], rdx
0x18000af40  lea     rdx, [rsp+58h+arg_8]
0x18000af45  mov     [rsp+58h+var_38], rdx
0x18000af4a  lea     edx, [r9+1]
0x18000af4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af53  inc     esi
0x18000af55  cmp     esi, [rdi+2408h]
0x18000af5b  jb      short loc_18000AF0C
0x18000af5d  mov     rcx, rbx; lpCriticalSection
0x18000af60  call    cs:__imp_LeaveCriticalSection
0x18000af66  jmp     short loc_18000AF72
0x18000af68  mov     dword ptr [rdi+2410h], 1
0x18000af72  mov     eax, ebp
0x18000af74  jmp     short loc_18000AF7B
0x18000af76  mov     eax, 80070057h
0x18000af7b  mov     rbx, [rsp+58h+arg_0]
0x18000af80  mov     rbp, [rsp+58h+arg_10]
0x18000af85  add     rsp, 40h
0x18000af89  pop     r14
0x18000af8b  pop     rdi
0x18000af8c  pop     rsi
0x18000af8d  retn
```
