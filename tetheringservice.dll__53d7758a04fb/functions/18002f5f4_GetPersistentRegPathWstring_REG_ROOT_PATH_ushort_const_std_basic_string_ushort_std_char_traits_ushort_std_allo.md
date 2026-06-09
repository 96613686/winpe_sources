# GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18002f5f4`
- end: `0x18002f7be`
- name: `?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002f7c4`

## callees

- `0x180002590`
- `0x18000fe0c`
- `0x180027090`
- `0x18002f468`
- `0x18002f5f4`

## import_xrefs

- `MobileNetworking!GetPersistentRegPath` at `0x18002f6cf`
- `MobileNetworking!GetPersistentRegPath` at `0x18002f6cf`

## pseudocode

```c
__int64 __fastcall GetPersistentRegPathWstring(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rdi
  unsigned int v6; // esi
  unsigned int v7; // eax
  __int128 *v8; // rcx
  __int128 *p_Src; // r9
  _WORD *v10; // rdi
  unsigned __int64 i; // rcx
  __int128 *v12; // r9
  unsigned int PersistentRegPath; // ebx
  unsigned int v14; // eax
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rcx
  __int128 *v17; // rcx
  unsigned __int64 v18; // rdx
  __int128 *v19; // r9
  _WORD *v20; // rdi
  unsigned __int64 j; // rcx
  int v23; // [rsp+30h] [rbp-58h] BYREF
  __int128 Src; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int64 v25; // [rsp+48h] [rbp-40h]
  unsigned __int64 v26; // [rsp+50h] [rbp-38h]

  Src = 0;
  v4 = 0;
  v25 = 0;
  v5 = 7;
  v26 = 7;
  LOWORD(Src) = 0;
  v6 = 0;
  v7 = 512;
  v23 = 512;
  try
  {
    while ( 1 )
    {
      if ( v7 > v4 )
      {
        if ( v7 - v4 > v5 - v4 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34__KG_Z__KG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0G_Z__KG_Z(&Src);
        }
        else
        {
          v25 = v7;
          p_Src = &Src;
          if ( v5 > 7 )
            p_Src = (__int128 *)Src;
          v10 = (_WORD *)p_Src + v4;
          if ( v7 != v4 )
          {
            for ( i = v7 - v4; i; --i )
              *v10++ = 0;
          }
          *((_WORD *)p_Src + v7) = 0;
        }
      }
      else
      {
        v25 = v7;
        v8 = &Src;
        if ( v5 > 7 )
          v8 = (__int128 *)Src;
        *((_WORD *)v8 + v7) = 0;
      }
      v12 = &Src;
      if ( v26 > 7 )
        v12 = (__int128 *)Src;
      PersistentRegPath = GetPersistentRegPath(13, L"Connections\\WWAN", &v23, v12);
      if ( PersistentRegPath != 234 )
        break;
      v14 = v6++;
      if ( v14 >= 3 )
        break;
      v5 = v26;
      v4 = v25;
      v7 = v23;
    }
    if ( !PersistentRegPath )
    {
      v15 = (unsigned int)(v23 - 1);
      v16 = v25;
      if ( v15 > v25 )
      {
        v18 = v15 - v25;
        if ( v15 - v25 > v26 - v25 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34__KG_Z__KG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0G_Z__KG_Z(&Src);
        }
        else
        {
          v25 = (unsigned int)(v23 - 1);
          v19 = &Src;
          if ( v26 > 7 )
            v19 = (__int128 *)Src;
          v20 = (_WORD *)v19 + v16;
          if ( v18 )
          {
            for ( j = v15 - v16; j; --j )
              *v20++ = 0;
          }
          *((_WORD *)v19 + v15) = 0;
        }
      }
      else
      {
        v25 = (unsigned int)(v23 - 1);
        v17 = &Src;
        if ( v26 > 7 )
          v17 = (__int128 *)Src;
        *((_WORD *)v17 + v15) = 0;
      }
      std::wstring::operator=(a3, &Src);
    }
    std::wstring::~wstring((char **)&Src);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( ... )
  {
    return 31;
  }
  return PersistentRegPath;
}

```

## disassembly

```asm
0x18002f5f4  push    rbx
0x18002f5f6  push    rsi
0x18002f5f7  push    rdi
0x18002f5f8  push    r14
0x18002f5fa  sub     rsp, 68h
0x18002f5fe  mov     rax, cs:__security_cookie
0x18002f605  xor     rax, rsp
0x18002f608  mov     [rsp+88h+var_30], rax
0x18002f60d  mov     r14, r8
0x18002f610  xorps   xmm0, xmm0
0x18002f613  movups  [rsp+88h+Src], xmm0
0x18002f618  xor     ecx, ecx
0x18002f61a  mov     [rsp+88h+var_40], rcx
0x18002f61f  lea     edi, [rcx+7]
0x18002f622  mov     [rsp+88h+var_38], rdi
0x18002f627  xor     eax, eax
0x18002f629  mov     word ptr [rsp+88h+Src], ax
0x18002f62e  xor     esi, esi
0x18002f630  mov     eax, 200h
0x18002f635  mov     [rsp+88h+var_58], eax
0x18002f639  mov     r8d, eax
0x18002f63c  cmp     r8, rcx
0x18002f63f  ja      short loc_18002F65E
0x18002f641  mov     [rsp+88h+var_40], r8
0x18002f646  lea     rcx, [rsp+88h+Src]
0x18002f64b  cmp     rdi, 7
0x18002f64f  cmova   rcx, qword ptr [rsp+88h+Src]
0x18002f655  xor     eax, eax
0x18002f657  mov     [rcx+r8*2], ax
0x18002f65c  jmp     short loc_18002F6AD
0x18002f65e  mov     rdx, r8
0x18002f661  sub     rdx, rcx
0x18002f664  mov     rax, rdi
0x18002f667  sub     rax, rcx
0x18002f66a  cmp     rdx, rax
0x18002f66d  ja      short loc_18002F6A0
0x18002f66f  mov     [rsp+88h+var_40], r8
0x18002f674  lea     r9, [rsp+88h+Src]
0x18002f679  cmp     rdi, 7
0x18002f67d  cmova   r9, qword ptr [rsp+88h+Src]
0x18002f683  lea     rdi, [r9+rcx*2]
0x18002f687  test    rdx, rdx
0x18002f68a  jz      short loc_18002F697
0x18002f68c  xor     eax, eax
0x18002f68e  movzx   eax, ax
0x18002f691  mov     rcx, rdx
0x18002f694  rep stosw
0x18002f697  xor     eax, eax
0x18002f699  mov     [r9+r8*2], ax
0x18002f69e  jmp     short loc_18002F6AD
0x18002f6a0  mov     r9, rdx
0x18002f6a3  lea     rcx, [rsp+88h+Src]; Src
0x18002f6a8  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18002f6ad  lea     r9, [rsp+88h+Src]
0x18002f6b2  cmp     [rsp+88h+var_38], 7
0x18002f6b8  cmova   r9, qword ptr [rsp+88h+Src]
0x18002f6be  lea     r8, [rsp+88h+var_58]
0x18002f6c3  lea     rdx, aConnectionsWwa; "Connections\\WWAN"
0x18002f6ca  mov     ecx, 0Dh
0x18002f6cf  call    cs:__imp_GetPersistentRegPath
0x18002f6d5  mov     ebx, eax
0x18002f6d7  cmp     eax, 0EAh
0x18002f6dc  jnz     short loc_18002F6FA
0x18002f6de  mov     eax, esi
0x18002f6e0  inc     esi
0x18002f6e2  cmp     eax, 3
0x18002f6e5  jnb     short loc_18002F6FA
0x18002f6e7  mov     rdi, [rsp+88h+var_38]
0x18002f6ec  mov     rcx, [rsp+88h+var_40]
0x18002f6f1  mov     eax, [rsp+88h+var_58]
0x18002f6f5  jmp     loc_18002F639
0x18002f6fa  test    ebx, ebx
0x18002f6fc  jnz     loc_18002F794
0x18002f702  mov     r8d, [rsp+88h+var_58]
0x18002f707  dec     r8d
0x18002f70a  mov     rcx, [rsp+88h+var_40]
0x18002f70f  cmp     r8, rcx
0x18002f712  ja      short loc_18002F733
0x18002f714  mov     [rsp+88h+var_40], r8
0x18002f719  lea     rcx, [rsp+88h+Src]
0x18002f71e  cmp     [rsp+88h+var_38], 7
0x18002f724  cmova   rcx, qword ptr [rsp+88h+Src]
0x18002f72a  xor     eax, eax
0x18002f72c  mov     [rcx+r8*2], ax
0x18002f731  jmp     short loc_18002F786
0x18002f733  mov     rdx, r8
0x18002f736  sub     rdx, rcx
0x18002f739  mov     rax, [rsp+88h+var_38]
0x18002f73e  sub     rax, rcx
0x18002f741  cmp     rdx, rax
0x18002f744  ja      short loc_18002F779
0x18002f746  mov     [rsp+88h+var_40], r8
0x18002f74b  lea     r9, [rsp+88h+Src]
0x18002f750  cmp     [rsp+88h+var_38], 7
0x18002f756  cmova   r9, qword ptr [rsp+88h+Src]
0x18002f75c  lea     rdi, [r9+rcx*2]
0x18002f760  test    rdx, rdx
0x18002f763  jz      short loc_18002F770
0x18002f765  xor     eax, eax
0x18002f767  movzx   eax, ax
0x18002f76a  mov     rcx, rdx
0x18002f76d  rep stosw
0x18002f770  xor     eax, eax
0x18002f772  mov     [r9+r8*2], ax
0x18002f777  jmp     short loc_18002F786
0x18002f779  mov     r9, rdx
0x18002f77c  lea     rcx, [rsp+88h+Src]; Src
0x18002f781  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18002f786  lea     rdx, [rsp+88h+Src]
0x18002f78b  mov     rcx, r14
0x18002f78e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002f793  nop
0x18002f794  lea     rcx, [rsp+88h+Src]
0x18002f799  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f79e  nop
0x18002f79f  jmp     short loc_18002F7A5
0x18002f7a1  mov     ebx, [rsp+88h+var_58]
0x18002f7a5  mov     eax, ebx
0x18002f7a7  mov     rcx, [rsp+88h+var_30]
0x18002f7ac  xor     rcx, rsp; StackCookie
0x18002f7af  call    __security_check_cookie
0x18002f7b4  add     rsp, 68h
0x18002f7b8  pop     r14
0x18002f7ba  pop     rdi
0x18002f7bb  pop     rsi
0x18002f7bc  pop     rbx
0x18002f7bd  retn
```
