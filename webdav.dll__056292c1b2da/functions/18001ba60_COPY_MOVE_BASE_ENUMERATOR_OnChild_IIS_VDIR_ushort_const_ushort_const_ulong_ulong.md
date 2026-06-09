# COPY_MOVE_BASE_ENUMERATOR::OnChild(IIS_VDIR *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18001ba60`
- end: `0x18001bc14`
- name: `?OnChild@COPY_MOVE_BASE_ENUMERATOR@@UEAAHPEAVIIS_VDIR@@PEBG1KK@Z`
- size: `436`
- prototype: `__int64 __fastcall(COPY_MOVE_BASE_ENUMERATOR *__hidden this, struct IIS_VDIR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800043b0`
- `0x18001ba60`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ba8e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ba8e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001baee`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001baee`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001bb22`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001bb22`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bb33`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bb33`

## pseudocode

```c
__int64 __fastcall COPY_MOVE_BASE_ENUMERATOR::OnChild(
        COPY_MOVE_BASE_ENUMERATOR *this,
        struct IIS_VDIR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6)
{
  int v10; // ebx
  unsigned int v11; // ebx
  int v13; // eax
  int v14; // r8d
  _BYTE v15[32]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v16; // [rsp+60h] [rbp-48h]

  STRU::STRU((STRU *)v15);
  v10 = (***((__int64 (__fastcall ****)(_QWORD, const unsigned __int16 *, _QWORD))this + 2))(
          *((_QWORD *)this + 2),
          a3,
          *((unsigned int *)this + 28));
  if ( v10 < 0 )
  {
    if ( (a6 & 0x10) == 0 )
      goto LABEL_3;
LABEL_18:
    v11 = 1;
    goto LABEL_4;
  }
  *(_WORD *)(*((_QWORD *)this + 10) + 2LL * *((unsigned int *)this + 27)) = 0;
  STRU::SyncWithBuffer((COPY_MOVE_BASE_ENUMERATOR *)((char *)this + 48));
  v10 = STRU::Append((COPY_MOVE_BASE_ENUMERATOR *)((char *)this + 48), &a3[*((unsigned int *)this + 26)]);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *))(**((_QWORD **)this + 2) + 8LL))(
            *((_QWORD *)this + 2),
            *((_QWORD *)this + 10),
            v15);
    if ( v10 >= 0 )
    {
      v13 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))this + 2))(
              *((_QWORD *)this + 2),
              *((_QWORD *)this + 10),
              2);
      v10 = v13;
      if ( v13 == -2147024893 )
      {
        if ( !STATIC_WSTRING_HASH::FindKey(
                *((STATIC_WSTRING_HASH **)this + 3),
                *((const unsigned __int16 **)this + 10),
                v14) )
          goto LABEL_3;
      }
      else if ( v13 < 0 )
      {
        goto LABEL_3;
      }
      v10 = (*(__int64 (__fastcall **)(COPY_MOVE_BASE_ENUMERATOR *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, __int64, unsigned int))(*(_QWORD *)this + 48LL))(
              this,
              a3,
              a4,
              *((_QWORD *)this + 10),
              v16,
              a6);
    }
  }
  if ( *((_DWORD *)this + 29) && (v10 == -2147024891 || v10 == -2147024893 || v10 == -2147024773) )
  {
    *((_DWORD *)this + 2) = v10;
    v11 = 0;
    goto LABEL_4;
  }
  *((_DWORD *)this + 29) = 0;
  if ( v10 >= 0 )
    goto LABEL_18;
LABEL_3:
  v11 = (*(__int64 (__fastcall **)(COPY_MOVE_BASE_ENUMERATOR *, struct IIS_VDIR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int))(*(_QWORD *)this + 16LL))(
          this,
          a2,
          a3,
          a4,
          a5,
          v10);
LABEL_4:
  STRU::~STRU((STRU *)v15);
  return v11;
}

```

## disassembly

```asm
0x18001ba60  push    rbx
0x18001ba62  push    rbp
0x18001ba63  push    rsi
0x18001ba64  push    rdi
0x18001ba65  push    r14
0x18001ba67  sub     rsp, 80h
0x18001ba6e  mov     rax, cs:__security_cookie
0x18001ba75  xor     rax, rsp
0x18001ba78  mov     [rsp+0A8h+var_30], rax
0x18001ba7d  mov     rdi, rcx
0x18001ba80  mov     rbp, r9
0x18001ba83  lea     rcx, [rsp+0A8h+var_68]
0x18001ba88  mov     rsi, r8
0x18001ba8b  mov     r14, rdx
0x18001ba8e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001ba94  mov     rcx, [rdi+10h]
0x18001ba98  mov     rdx, rsi
0x18001ba9b  mov     r8d, [rdi+70h]
0x18001ba9f  mov     rax, [rcx]
0x18001baa2  mov     rax, [rax]
0x18001baa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baaa  mov     ebx, eax
0x18001baac  test    eax, eax
0x18001baae  jns     short loc_18001BB11
0x18001bab0  test    byte ptr [rsp+0A8h+arg_28], 10h
0x18001bab8  jnz     loc_18001BC0A
0x18001babe  mov     rax, [rdi]
0x18001bac1  mov     r9, rbp
0x18001bac4  mov     r10d, [rsp+0A8h+arg_20]
0x18001bacc  mov     r8, rsi
0x18001bacf  mov     [rsp+0A8h+var_80], ebx
0x18001bad3  mov     rdx, r14
0x18001bad6  mov     rcx, rdi
0x18001bad9  mov     dword ptr [rsp+0A8h+var_88], r10d
0x18001bade  mov     rax, [rax+10h]
0x18001bae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bae7  mov     ebx, eax
0x18001bae9  lea     rcx, [rsp+0A8h+var_68]
0x18001baee  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001baf4  mov     eax, ebx
0x18001baf6  mov     rcx, [rsp+0A8h+var_30]
0x18001bafb  xor     rcx, rsp; StackCookie
0x18001bafe  call    __security_check_cookie
0x18001bb03  add     rsp, 80h
0x18001bb0a  pop     r14
0x18001bb0c  pop     rdi
0x18001bb0d  pop     rsi
0x18001bb0e  pop     rbp
0x18001bb0f  pop     rbx
0x18001bb10  retn
0x18001bb11  mov     rcx, [rdi+50h]
0x18001bb15  xor     eax, eax
0x18001bb17  mov     edx, [rdi+6Ch]
0x18001bb1a  mov     [rcx+rdx*2], ax
0x18001bb1e  lea     rcx, [rdi+30h]
0x18001bb22  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001bb28  mov     eax, [rdi+68h]
0x18001bb2b  lea     rcx, [rdi+30h]
0x18001bb2f  lea     rdx, [rsi+rax*2]
0x18001bb33  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001bb39  mov     ebx, eax
0x18001bb3b  test    eax, eax
0x18001bb3d  js      loc_18001BBD3
0x18001bb43  mov     rcx, [rdi+10h]
0x18001bb47  lea     r8, [rsp+0A8h+var_68]
0x18001bb4c  mov     rdx, [rdi+50h]
0x18001bb50  mov     rax, [rcx]
0x18001bb53  mov     rax, [rax+8]
0x18001bb57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb5c  mov     ebx, eax
0x18001bb5e  test    eax, eax
0x18001bb60  js      short loc_18001BBD3
0x18001bb62  mov     rcx, [rdi+10h]
0x18001bb66  mov     r8d, 2
0x18001bb6c  mov     rdx, [rdi+50h]
0x18001bb70  mov     rax, [rcx]
0x18001bb73  mov     rax, [rax]
0x18001bb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb7b  mov     ebx, eax
0x18001bb7d  cmp     eax, 80070003h
0x18001bb82  jnz     short loc_18001BB9B
0x18001bb84  mov     rdx, [rdi+50h]; unsigned __int16 *
0x18001bb88  mov     rcx, [rdi+18h]; this
0x18001bb8c  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x18001bb91  test    rax, rax
0x18001bb94  jnz     short loc_18001BBA3
0x18001bb96  jmp     loc_18001BABE
0x18001bb9b  test    eax, eax
0x18001bb9d  js      loc_18001BABE
0x18001bba3  mov     rdx, [rsp+0A8h+var_48]
0x18001bba8  mov     r8, rbp
0x18001bbab  mov     rax, [rdi]
0x18001bbae  mov     ecx, [rsp+0A8h+arg_28]
0x18001bbb5  mov     r9, [rdi+50h]
0x18001bbb9  mov     [rsp+0A8h+var_80], ecx
0x18001bbbd  mov     rcx, rdi
0x18001bbc0  mov     rax, [rax+30h]
0x18001bbc4  mov     [rsp+0A8h+var_88], rdx
0x18001bbc9  mov     rdx, rsi
0x18001bbcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbd1  mov     ebx, eax
0x18001bbd3  cmp     dword ptr [rdi+74h], 0
0x18001bbd7  jz      short loc_18001BBFB
0x18001bbd9  cmp     ebx, 80070005h
0x18001bbdf  jz      short loc_18001BBF1
0x18001bbe1  cmp     ebx, 80070003h
0x18001bbe7  jz      short loc_18001BBF1
0x18001bbe9  cmp     ebx, 8007007Bh
0x18001bbef  jnz     short loc_18001BBFB
0x18001bbf1  mov     [rdi+8], ebx
0x18001bbf4  xor     ebx, ebx
0x18001bbf6  jmp     loc_18001BAE9
0x18001bbfb  mov     dword ptr [rdi+74h], 0
0x18001bc02  test    ebx, ebx
0x18001bc04  js      loc_18001BABE
0x18001bc0a  mov     ebx, 1
0x18001bc0f  jmp     loc_18001BAE9
```
