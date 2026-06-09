# Tpm20ResourceMgr::CacheResponse(void *,uint,void const *,uint)

- ea: `0x14000efc0`
- end: `0x14000f3fc`
- name: `?CacheResponse@Tpm20ResourceMgr@@AEAAXPEAXIPEBXI@Z`
- size: `1084`
- prototype: `void __usercall(Tpm20ResourceMgr *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const void *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140016afc`

## callees

- `0x1400078b8`
- `0x140009278`
- `0x14000efc0`
- `0x140010cb0`
- `0x1400133c8`
- `0x140013490`
- `0x140039840`
- `0x140045430`
- `0x1400454a0`

## pseudocode

```c
void __fastcall Tpm20ResourceMgr::CacheResponse(
        Tpm20ResourceMgr *this,
        char *a2,
        __int64 a3,
        char *a4,
        unsigned int Size)
{
  __int16 v6; // ax
  __int64 v8; // r9
  int i; // ecx
  __int64 v10; // rbx
  char *v11; // rsi
  unsigned __int32 v12; // ecx
  unsigned __int32 v13; // ebx
  int PublicBufferIndexFromHandle; // eax
  Tpm20ResourceMgr *v15; // rcx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  void *v18; // rcx
  unsigned __int8 *v19; // rax
  char *v20; // rdx
  unsigned __int8 *v21; // rax
  unsigned __int64 retaddr; // [rsp+38h] [rbp+0h]

  v6 = __ROR2__(*(_WORD *)a2, 8);
  if ( v6 != -32766 )
  {
    if ( v6 != -32767 || _byteswap_ulong(*(_DWORD *)(a2 + 6)) - 322 > 1 )
    {
LABEL_4:
      if ( (_DWORD)a3 == 14 )
      {
        if ( v6 == -32767 && _byteswap_ulong(*(_DWORD *)(a2 + 6)) == 371 && _byteswap_ulong(*(_DWORD *)(a2 + 2)) == 14 )
        {
          v8 = _byteswap_ulong(*(_DWORD *)(a2 + 10));
          if ( (v8 & 0xFF000000) == 0x81000000 )
          {
            for ( i = 0; ; ++i )
            {
              if ( i >= 5 )
              {
                for ( i = 0; i < 5; ++i )
                {
                  v20 = (char *)this + 4 * i;
                  if ( !*((_DWORD *)v20 + 34) )
                  {
                    *((_DWORD *)v20 + 34) = v8;
                    goto LABEL_14;
                  }
                }
                goto LABEL_37;
              }
              if ( *((_DWORD *)this + i + 34) == (_DWORD)v8 )
                break;
            }
LABEL_14:
            if ( i != -1 )
            {
              v10 = i;
              v11 = (char *)this + 8 * i;
              if ( !*((_QWORD *)v11 + 12) || !*((_DWORD *)this + i + 18) )
              {
                v19 = TpmAlloc(1, Size, retaddr);
                *((_QWORD *)v11 + 12) = v19;
                if ( v19 )
                {
                  memmove(v19, a4, Size);
                  *((_DWORD *)this + v10 + 18) = Size;
                }
                else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids);
                }
              }
              return;
            }
LABEL_37:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids, v8);
            }
          }
        }
      }
      else if ( (_DWORD)a3 == 10
             && v6 == -32767
             && _byteswap_ulong(*(_DWORD *)(a2 + 6)) == 380
             && _byteswap_ulong(*(_DWORD *)(a2 + 2)) == 10
             && (!*((_QWORD *)this + 20) || !*((_DWORD *)this + 39))
             && !_byteswap_ulong(*(_DWORD *)&a4[(unsigned __int16)__ROR2__(*((_WORD *)a4 + 5), 8) + 12]) )
      {
        v21 = TpmAlloc(1, Size, retaddr);
        *((_QWORD *)this + 20) = v21;
        if ( v21 )
        {
          memmove(v21, a4, Size);
          *((_DWORD *)this + 39) = Size;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids);
        }
      }
      return;
    }
    if ( !*((_QWORD *)this + 20) )
      return;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids);
    v18 = (void *)*((_QWORD *)this + 20);
LABEL_46:
    TpmFree(v18);
    *((_QWORD *)this + 20) = 0;
    *((_DWORD *)this + 39) = 0;
    return;
  }
  v12 = _byteswap_ulong(*(_DWORD *)(a2 + 6));
  if ( v12 != 288 )
  {
    if ( v12 != 294 )
      goto LABEL_4;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids);
    Tpm20ResourceMgr::CleanAllCachedResponses(this);
    v18 = (void *)*((_QWORD *)this + 20);
    if ( !v18 )
      return;
    goto LABEL_46;
  }
  v13 = _byteswap_ulong(*(_DWORD *)(a2 + 14));
  if ( v13 == _byteswap_ulong(*(_DWORD *)&a2[_byteswap_ulong(*(_DWORD *)(a2 + 18)) + 22])
    && (v13 & 0xFF000000) == 0x81000000 )
  {
    PublicBufferIndexFromHandle = Tpm20ResourceMgr::GetCachedReadPublicBufferIndexFromHandle(this, v13, a3, 32769);
    if ( PublicBufferIndexFromHandle == -1 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        return;
      v17 = 51;
    }
    else
    {
      if ( !(unsigned int)Tpm20ResourceMgr::CleanCachedReadPublicResponse(v15, PublicBufferIndexFromHandle) )
        return;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        return;
      v17 = 52;
    }
    WPP_SF_d(v16->AttachedDevice, v17, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids, v13);
  }
}

```

## disassembly

```asm
0x14000efc0  push    rbx
0x14000efc2  push    rdi
0x14000efc3  push    r13
0x14000efc5  sub     rsp, 20h
0x14000efc9  movzx   eax, word ptr [rdx]
0x14000efcc  mov     rdi, rcx
0x14000efcf  ror     ax, 8
0x14000efd3  mov     ecx, 8002h
0x14000efd8  mov     r13, r9
0x14000efdb  mov     r9d, 8001h
0x14000efe1  cmp     ax, cx
0x14000efe4  jz      loc_14000F0AE
0x14000efea  cmp     ax, r9w
0x14000efee  jnz     short loc_14000F004
0x14000eff0  mov     ecx, [rdx+6]
0x14000eff3  bswap   ecx
0x14000eff5  sub     ecx, 142h
0x14000effb  cmp     ecx, 1
0x14000effe  jbe     loc_14000F2A6
0x14000f004  mov     [rsp+38h+arg_8], rsi
0x14000f009  cmp     r8d, 0Eh
0x14000f00d  jz      short loc_14000F028
0x14000f00f  cmp     r8d, 0Ah
0x14000f013  jz      loc_14000F32F
0x14000f019  mov     rsi, [rsp+38h+arg_8]
0x14000f01e  add     rsp, 20h
0x14000f022  pop     r13
0x14000f024  pop     rdi
0x14000f025  pop     rbx
0x14000f026  retn
0x14000f028  cmp     ax, r9w
0x14000f02c  jnz     short loc_14000F019
0x14000f02e  mov     eax, [rdx+6]
0x14000f031  bswap   eax
0x14000f033  cmp     eax, 173h
0x14000f038  jnz     short loc_14000F019
0x14000f03a  mov     eax, [rdx+2]
0x14000f03d  bswap   eax
0x14000f03f  cmp     eax, 0Eh
0x14000f042  jnz     short loc_14000F019
0x14000f044  mov     r9d, [rdx+0Ah]
0x14000f048  bswap   r9d
0x14000f04b  mov     eax, r9d
0x14000f04e  and     eax, 0FF000000h
0x14000f053  cmp     eax, 81000000h
0x14000f058  jnz     short loc_14000F019
0x14000f05a  xor     edx, edx
0x14000f05c  mov     ecx, edx
0x14000f05e  cmp     ecx, 5
0x14000f061  jge     loc_14000F1DA
0x14000f067  movsxd  rax, ecx
0x14000f06a  cmp     [rdi+rax*4+88h], r9d
0x14000f072  jnz     loc_14000F126
0x14000f078  cmp     ecx, 0FFFFFFFFh
0x14000f07b  jz      loc_14000F1E5
0x14000f081  movsxd  rbx, ecx
0x14000f084  cmp     qword ptr [rdi+rbx*8+60h], 0
0x14000f08a  lea     rsi, [rdi+rbx*8]
0x14000f08e  mov     [rsp+38h+arg_0], rbp
0x14000f093  jz      loc_14000F185
0x14000f099  cmp     dword ptr [rdi+rbx*4+48h], 0
0x14000f09e  jz      loc_14000F185
0x14000f0a4  mov     rbp, [rsp+38h+arg_0]
0x14000f0a9  jmp     loc_14000F019
0x14000f0ae  mov     ecx, [rdx+6]
0x14000f0b1  bswap   ecx
0x14000f0b3  cmp     ecx, 120h
0x14000f0b9  jnz     short loc_14000F12D
0x14000f0bb  mov     eax, [rdx+12h]
0x14000f0be  mov     ebx, [rdx+0Eh]
0x14000f0c1  bswap   eax
0x14000f0c3  add     eax, 16h
0x14000f0c6  bswap   ebx
0x14000f0c8  mov     ecx, [rax+rdx]
0x14000f0cb  bswap   ecx
0x14000f0cd  cmp     ebx, ecx
0x14000f0cf  jnz     loc_14000F01E
0x14000f0d5  mov     eax, ebx
0x14000f0d7  and     eax, 0FF000000h
0x14000f0dc  cmp     eax, 81000000h
0x14000f0e1  jnz     loc_14000F01E
0x14000f0e7  mov     edx, ebx
0x14000f0e9  mov     rcx, rdi
0x14000f0ec  call    ?GetCachedReadPublicBufferIndexFromHandle@Tpm20ResourceMgr@@AEAAHT_TPM20_HANDLE@@@Z; Tpm20ResourceMgr::GetCachedReadPublicBufferIndexFromHandle(_TPM20_HANDLE)
0x14000f0f1  cmp     eax, 0FFFFFFFFh
0x14000f0f4  jnz     loc_14000F23E
0x14000f0fa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f101  lea     rax, WPP_GLOBAL_Control
0x14000f108  cmp     rcx, rax
0x14000f10b  jz      loc_14000F01E
0x14000f111  mov     eax, [rcx+2Ch]
0x14000f114  test    al, 4
0x14000f116  jz      loc_14000F01E
0x14000f11c  mov     edx, 33h ; '3'
0x14000f121  jmp     loc_14000F226
0x14000f126  inc     ecx
0x14000f128  jmp     loc_14000F05E
0x14000f12d  cmp     ecx, 126h
0x14000f133  jnz     loc_14000F004
0x14000f139  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f140  lea     rax, WPP_GLOBAL_Control
0x14000f147  cmp     rcx, rax
0x14000f14a  jz      short loc_14000F168
0x14000f14c  mov     eax, [rcx+2Ch]
0x14000f14f  test    al, 4
0x14000f151  jz      short loc_14000F168
0x14000f153  mov     rcx, [rcx+18h]
0x14000f157  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000f15e  mov     edx, 35h ; '5'
0x14000f163  call    WPP_SF_
0x14000f168  mov     rcx, rdi; this
0x14000f16b  call    ?CleanAllCachedResponses@Tpm20ResourceMgr@@QEAAXXZ; Tpm20ResourceMgr::CleanAllCachedResponses(void)
0x14000f170  mov     rcx, [rdi+0A0h]
0x14000f177  test    rcx, rcx
0x14000f17a  jz      loc_14000F01E
0x14000f180  jmp     loc_14000F28D
0x14000f185  mov     r8, [rsp+38h]; unsigned __int64
0x14000f18a  mov     cl, 1; bool
0x14000f18c  mov     [rsp+38h+arg_10], r14
0x14000f191  mov     ebp, 12h
0x14000f196  mov     r14d, dword ptr [rsp+38h+Size]
0x14000f19b  mov     edx, r14d; unsigned __int64
0x14000f19e  mov     [rsp+38h+arg_18], r15
0x14000f1a3  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14000f1a8  mov     [rsi+60h], rax
0x14000f1ac  test    rax, rax
0x14000f1af  jz      loc_14000F2F3
0x14000f1b5  mov     r8d, r14d; Size
0x14000f1b8  mov     rdx, r13; Src
0x14000f1bb  mov     rcx, rax; void *
0x14000f1be  call    memmove
0x14000f1c3  lea     rax, [rbx+rbp]
0x14000f1c7  mov     [rdi+rax*4], r14d
0x14000f1cb  mov     r14, [rsp+38h+arg_10]
0x14000f1d0  mov     r15, [rsp+38h+arg_18]
0x14000f1d5  jmp     loc_14000F0A4
0x14000f1da  mov     ecx, edx
0x14000f1dc  cmp     ecx, 5
0x14000f1df  jl      loc_14000F2D0
0x14000f1e5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f1ec  lea     rax, WPP_GLOBAL_Control
0x14000f1f3  cmp     rcx, rax
0x14000f1f6  jz      loc_14000F019
0x14000f1fc  mov     eax, [rcx+2Ch]
0x14000f1ff  test    al, 4
0x14000f201  jz      loc_14000F019
0x14000f207  mov     rcx, [rcx+18h]
0x14000f20b  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000f212  mov     edx, 37h ; '7'
0x14000f217  call    WPP_SF_d
0x14000f21c  jmp     loc_14000F019
0x14000f221  mov     edx, 34h ; '4'
0x14000f226  mov     rcx, [rcx+18h]
0x14000f22a  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000f231  mov     r9d, ebx
0x14000f234  call    WPP_SF_d
0x14000f239  jmp     loc_14000F01E
0x14000f23e  mov     edx, eax; int
0x14000f240  call    ?CleanCachedReadPublicResponse@Tpm20ResourceMgr@@AEAAHH@Z; Tpm20ResourceMgr::CleanCachedReadPublicResponse(int)
0x14000f245  test    eax, eax
0x14000f247  jz      loc_14000F01E
0x14000f24d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f254  lea     rax, WPP_GLOBAL_Control
0x14000f25b  cmp     rcx, rax
0x14000f25e  jz      loc_14000F01E
0x14000f264  mov     eax, [rcx+2Ch]
0x14000f267  test    al, 4
0x14000f269  jz      loc_14000F01E
0x14000f26f  jmp     short loc_14000F221
0x14000f271  mov     rcx, [rcx+18h]
0x14000f275  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000f27c  mov     edx, 36h ; '6'
0x14000f281  call    WPP_SF_
0x14000f286  mov     rcx, [rdi+0A0h]; void *
0x14000f28d  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14000f292  xor     edx, edx
0x14000f294  mov     [rdi+0A0h], rdx
0x14000f29b  mov     [rdi+9Ch], edx
0x14000f2a1  jmp     loc_14000F01E
0x14000f2a6  cmp     qword ptr [rdi+0A0h], 0
0x14000f2ae  jz      loc_14000F01E
0x14000f2b4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f2bb  lea     rax, WPP_GLOBAL_Control
0x14000f2c2  cmp     rcx, rax
0x14000f2c5  jz      short loc_14000F286
0x14000f2c7  mov     eax, [rcx+2Ch]
0x14000f2ca  test    al, 4
0x14000f2cc  jz      short loc_14000F286
0x14000f2ce  jmp     short loc_14000F271
0x14000f2d0  movsxd  rax, ecx
0x14000f2d3  lea     rdx, [rdi+rax*4]
0x14000f2d7  cmp     dword ptr [rdx+88h], 0
0x14000f2de  jz      short loc_14000F2E7
0x14000f2e0  inc     ecx
0x14000f2e2  jmp     loc_14000F1DC
0x14000f2e7  mov     [rdx+88h], r9d
0x14000f2ee  jmp     loc_14000F078
0x14000f2f3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f2fa  lea     rax, WPP_GLOBAL_Control
0x14000f301  cmp     rcx, rax
0x14000f304  jz      loc_14000F1CB
0x14000f30a  mov     eax, [rcx+2Ch]
0x14000f30d  test    al, 4
0x14000f30f  jz      loc_14000F1CB
0x14000f315  mov     rcx, [rcx+18h]
0x14000f319  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000f320  mov     edx, 38h ; '8'
0x14000f325  call    WPP_SF_
0x14000f32a  jmp     loc_14000F1CB
0x14000f32f  cmp     ax, r9w
0x14000f333  jnz     loc_14000F019
0x14000f339  mov     eax, [rdx+6]
0x14000f33c  bswap   eax
0x14000f33e  cmp     eax, 17Ch
0x14000f343  jnz     loc_14000F019
0x14000f349  mov     eax, [rdx+2]
0x14000f34c  bswap   eax
0x14000f34e  cmp     eax, 0Ah
0x14000f351  jnz     loc_14000F019
0x14000f357  cmp     qword ptr [rdi+0A0h], 0
0x14000f35f  jz      short loc_14000F36E
0x14000f361  cmp     dword ptr [rdi+9Ch], 0
0x14000f368  jnz     loc_14000F019
0x14000f36e  movzx   eax, word ptr [r13+0Ah]
0x14000f373  ror     ax, 8
0x14000f377  movzx   eax, ax
0x14000f37a  mov     ecx, [rax+r13+0Ch]
0x14000f37f  bswap   ecx
0x14000f381  test    ecx, ecx
0x14000f383  jnz     loc_14000F019
0x14000f389  mov     ebx, dword ptr [rsp+38h+Size]
0x14000f38d  mov     cl, 1; bool
0x14000f38f  mov     r8, [rsp+38h]; unsigned __int64
0x14000f394  mov     edx, ebx; unsigned __int64
0x14000f396  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14000f39b  mov     [rdi+0A0h], rax
0x14000f3a2  test    rax, rax
0x14000f3a5  jnz     short loc_14000F3E3
0x14000f3a7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f3ae  lea     rax, WPP_GLOBAL_Control
0x14000f3b5  cmp     rcx, rax
0x14000f3b8  jz      loc_14000F019
0x14000f3be  mov     eax, [rcx+2Ch]
0x14000f3c1  test    al, 4
0x14000f3c3  jz      loc_14000F019
0x14000f3c9  mov     rcx, [rcx+18h]
0x14000f3cd  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000f3d4  mov     edx, 39h ; '9'
0x14000f3d9  call    WPP_SF_
0x14000f3de  jmp     loc_14000F019
0x14000f3e3  mov     r8, rbx; Size
0x14000f3e6  mov     rdx, r13; Src
0x14000f3e9  mov     rcx, rax; void *
0x14000f3ec  call    memmove
0x14000f3f1  mov     [rdi+9Ch], ebx
0x14000f3f7  jmp     loc_14000F019
```
