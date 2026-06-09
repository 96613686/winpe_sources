# CVaultMemoryStore::UpdateCredCountPerAppContainer(void *,int)

- ea: `0x180024ebc`
- end: `0x180025061`
- name: `?UpdateCredCountPerAppContainer@CVaultMemoryStore@@IEAAKPEAXH@Z`
- size: `421`
- prototype: `unsigned int(CVaultMemoryStore *__hidden this, void *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024520`
- `0x180024b08`

## callees

- `0x180024ebc`
- `0x180029278`
- `0x18003a580`
- `0x18003af10`
- `0x18004b430`
- `0x18004b43c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180024f0c`
- `ntdll!RtlLengthSid` at `0x180024f0c`

## pseudocode

```c
__int64 __fastcall CVaultMemoryStore::UpdateCredCountPerAppContainer(CVaultMemoryStore *this, void *a2, int a3)
{
  ULONG v6; // eax
  char *v7; // r15
  __int64 *v8; // r14
  __int64 *v9; // rdi
  __int64 *v10; // rbx
  char v11; // cl
  __int64 *v12; // rax
  int v14; // eax
  int v15; // eax
  _BYTE v17[12]; // [rsp+20h] [rbp-F8h] BYREF
  int v18; // [rsp+2Ch] [rbp-ECh]
  _OWORD Buf2[4]; // [rsp+40h] [rbp-D8h] BYREF
  int v20; // [rsp+80h] [rbp-98h]
  _OWORD v21[4]; // [rsp+90h] [rbp-88h] BYREF
  int v22; // [rsp+D0h] [rbp-48h]
  int v23; // [rsp+D4h] [rbp-44h]

  if ( !a2 )
    return 0;
  memset_0(Buf2, 0, 0x44u);
  v6 = RtlLengthSid(a2);
  memcpy_0(Buf2, a2, v6);
  v7 = (char *)this + 40;
  v8 = (__int64 *)*((_QWORD *)this + 5);
  v9 = (__int64 *)v8[1];
  v18 = 0;
  v10 = v8;
  if ( !*((_BYTE *)v9 + 25) )
  {
    do
    {
      if ( memcmp_0((char *)v9 + 28, Buf2, 0x44u) >= 0 )
      {
        v11 = 0;
        v10 = v9;
      }
      else
      {
        v11 = 1;
      }
      v12 = v9 + 2;
      if ( !v11 )
        v12 = v9;
      v9 = (__int64 *)*v12;
    }
    while ( !*(_BYTE *)(*v12 + 25) );
  }
  if ( *((_BYTE *)v10 + 25) || memcmp_0(Buf2, (char *)v10 + 28, 0x44u) < 0 )
    v10 = v8;
  if ( v10 == v8 )
  {
    if ( a3 )
    {
      try
      {
        v21[0] = Buf2[0];
        v21[1] = Buf2[1];
        v21[2] = Buf2[2];
        v21[3] = Buf2[3];
        v22 = v20;
        v23 = 1;
        std::_Tree<std::_Tmap_traits<_tagSIDArray,unsigned long,SidCmp,std::allocator<std::pair<_tagSIDArray const,unsigned long>>,0>>::_Emplace<std::pair<_tagSIDArray,int>>(
          v7,
          v17,
          v21);
      }
      catch ( std::bad_alloc )
      {
        return 14;
      }
      return 0;
    }
    return 1168;
  }
  else
  {
    v14 = *((_DWORD *)v10 + 24);
    if ( a3 )
    {
      v15 = v14 + 1;
LABEL_17:
      *((_DWORD *)v10 + 24) = v15;
      return 0;
    }
    if ( v14 )
    {
      v15 = v14 - 1;
      goto LABEL_17;
    }
    return 13;
  }
}

```

## disassembly

```asm
0x180024ebc  mov     [rsp+arg_10], rbx
0x180024ec1  push    rsi
0x180024ec2  push    rdi
0x180024ec3  push    r13
0x180024ec5  push    r14
0x180024ec7  push    r15
0x180024ec9  sub     rsp, 0F0h
0x180024ed0  mov     rax, cs:__security_cookie
0x180024ed7  xor     rax, rsp
0x180024eda  mov     [rsp+118h+var_38], rax
0x180024ee2  mov     esi, r8d
0x180024ee5  mov     rbx, rdx
0x180024ee8  mov     rdi, rcx
0x180024eeb  test    rdx, rdx
0x180024eee  jz      loc_180024F9D
0x180024ef4  mov     r13d, 44h ; 'D'
0x180024efa  mov     r8d, r13d; Size
0x180024efd  xor     edx, edx; Val
0x180024eff  lea     rcx, [rsp+118h+Buf2]; void *
0x180024f04  call    memset_0
0x180024f09  mov     rcx, rbx; Sid
0x180024f0c  call    cs:__imp_RtlLengthSid
0x180024f12  mov     r8d, eax; Size
0x180024f15  mov     rdx, rbx; Src
0x180024f18  lea     rcx, [rsp+118h+Buf2]; void *
0x180024f1d  call    memcpy_0
0x180024f22  lea     r15, [rdi+28h]
0x180024f26  mov     r14, [r15]
0x180024f29  mov     rdi, [r14+8]
0x180024f2d  xor     eax, eax
0x180024f2f  mov     [rsp+118h+var_EC], eax
0x180024f33  mov     rbx, r14
0x180024f36  cmp     [rdi+19h], al
0x180024f39  jnz     short loc_180024F65
0x180024f3b  lea     rcx, [rdi+1Ch]; Buf1
0x180024f3f  mov     r8, r13; Size
0x180024f42  lea     rdx, [rsp+118h+Buf2]; Buf2
0x180024f47  call    memcmp_0
0x180024f4c  test    eax, eax
0x180024f4e  jns     short loc_180024FC7
0x180024f50  mov     cl, 1
0x180024f52  lea     rax, [rdi+10h]
0x180024f56  test    cl, cl
0x180024f58  cmovz   rax, rdi
0x180024f5c  mov     rdi, [rax]
0x180024f5f  cmp     byte ptr [rdi+19h], 0
0x180024f63  jz      short loc_180024F3B
0x180024f65  cmp     byte ptr [rbx+19h], 0
0x180024f69  jnz     short loc_180024F84
0x180024f6b  lea     rdx, [rbx+1Ch]; Buf2
0x180024f6f  mov     r8, r13; Size
0x180024f72  lea     rcx, [rsp+118h+Buf2]; Buf1
0x180024f77  call    memcmp_0
0x180024f7c  test    eax, eax
0x180024f7e  js      short loc_180024F84
0x180024f80  mov     al, 1
0x180024f82  jmp     short loc_180024F86
0x180024f84  xor     al, al
0x180024f86  test    al, al
0x180024f88  cmovz   rbx, r14
0x180024f8c  cmp     rbx, r14
0x180024f8f  jz      short loc_180024FDA
0x180024f91  mov     eax, [rbx+60h]
0x180024f94  test    esi, esi
0x180024f96  jz      short loc_180024FCE
0x180024f98  inc     eax
0x180024f9a  mov     [rbx+60h], eax
0x180024f9d  xor     eax, eax
0x180024f9f  mov     rcx, [rsp+118h+var_38]
0x180024fa7  xor     rcx, rsp; StackCookie
0x180024faa  call    __security_check_cookie
0x180024faf  mov     rbx, [rsp+118h+arg_10]
0x180024fb7  add     rsp, 0F0h
0x180024fbe  pop     r15
0x180024fc0  pop     r14
0x180024fc2  pop     r13
0x180024fc4  pop     rdi
0x180024fc5  pop     rsi
0x180024fc6  retn
0x180024fc7  xor     cl, cl
0x180024fc9  mov     rbx, rdi
0x180024fcc  jmp     short loc_180024F52
0x180024fce  test    eax, eax
0x180024fd0  jz      loc_180025057
0x180024fd6  dec     eax
0x180024fd8  jmp     short loc_180024F9A
0x180024fda  test    esi, esi
0x180024fdc  jnz     short loc_180024FE5
0x180024fde  mov     eax, 490h
0x180024fe3  jmp     short loc_180024F9F
0x180024fe5  movaps  xmm0, [rsp+118h+Buf2]
0x180024fea  movaps  [rsp+118h+var_88], xmm0
0x180024ff2  movaps  xmm1, [rsp+118h+var_C8]
0x180024ff7  movaps  [rsp+118h+var_78], xmm1
0x180024fff  movaps  xmm0, [rsp+118h+var_B8]
0x180025004  movaps  [rsp+118h+var_68], xmm0
0x18002500c  movaps  xmm1, [rsp+118h+var_A8]
0x180025011  movaps  [rsp+118h+var_58], xmm1
0x180025019  mov     eax, [rsp+118h+var_98]
0x180025020  mov     [rsp+118h+var_48], eax
0x180025027  mov     [rsp+118h+var_44], 1
0x180025032  lea     r8, [rsp+118h+var_88]
0x18002503a  lea     rdx, [rsp+118h+var_F8]
0x18002503f  mov     rcx, r15
0x180025042  call    ??$_Emplace@U?$pair@U_tagSIDArray@@H@std@@@?$_Tree@V?$_Tmap_traits@U_tagSIDArray@@KUSidCmp@@V?$allocator@U?$pair@$$CBU_tagSIDArray@@K@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_tagSIDArray@@K@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_tagSIDArray@@H@1@@Z; std::_Tree<std::_Tmap_traits<_tagSIDArray,ulong,SidCmp,std::allocator<std::pair<_tagSIDArray const,ulong>>,0>>::_Emplace<std::pair<_tagSIDArray,int>>(std::pair<_tagSIDArray,int> &&)
0x180025047  nop
0x180025048  jmp     loc_180024F9D
0x18002504d  mov     eax, 0Eh
0x180025052  jmp     loc_180024F9F
0x180025057  mov     eax, 0Dh
0x18002505c  jmp     loc_180024F9F
```
