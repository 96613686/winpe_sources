# AutoProxyBase::SetOptions(tagProxyOptions const *)

- ea: `0x180071ae0`
- end: `0x180071d92`
- name: `?SetOptions@AutoProxyBase@@UEAAJPEBUtagProxyOptions@@@Z`
- size: `690`
- prototype: `__int64 __fastcall(AutoProxyBase *__hidden this, const struct tagProxyOptions *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c2a60`

## callees

- `0x180071ae0`
- `0x1800db6b0`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180071b28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180071b28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071c52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071b6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071b6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071c3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071c3d`

## pseudocode

```c
__int64 __fastcall AutoProxyBase::SetOptions(AutoProxyBase *this, const struct tagProxyOptions *a2)
{
  __int64 *v4; // rsi
  _OWORD *v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-48h]

  v4 = (__int64 *)((char *)this + 240);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qq(1029, 22, (unsigned int)WPP_8f662043cd0431ebe0ccb29223685825_Traceguids, (_DWORD)a2, *v4);
  if ( a2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    if ( *v4 )
    {
      v6 = -2147024809;
    }
    else
    {
      if ( (xmmword_180107A60 & 0x20) != 0 )
        WPP_SF_qq(1029, 11, (unsigned int)WPP_23d61de28852329ea54c9edce07bfeba_Traceguids, (_DWORD)a2, (__int64)v4);
      if ( v4 )
      {
        *v4 = 0;
        v5 = CoTaskMemAlloc(0x38u);
        if ( v5 )
        {
          *v5 = 0;
          v5[1] = 0;
          v5[2] = 0;
          *((_QWORD *)v5 + 6) = 0;
          if ( (xmmword_180107A60 & 0x20) != 0 )
            WPP_SF_qq(1029, 10, (unsigned int)WPP_23d61de28852329ea54c9edce07bfeba_Traceguids, (_DWORD)a2, (__int64)v5);
          v6 = 0;
          *(_DWORD *)v5 = *(_DWORD *)a2;
          *((_DWORD *)v5 + 1) = *((_DWORD *)a2 + 1);
          *((_DWORD *)v5 + 2) = *((_DWORD *)a2 + 2);
          *((_DWORD *)v5 + 5) = *((_DWORD *)a2 + 5);
          *((_DWORD *)v5 + 3) = *((_DWORD *)a2 + 3);
          *((_DWORD *)v5 + 4) = *((_DWORD *)a2 + 4);
          *((_DWORD *)v5 + 6) = *((_DWORD *)a2 + 6);
          *((_DWORD *)v5 + 7) = *((_DWORD *)a2 + 7);
          *((_DWORD *)v5 + 8) = *((_DWORD *)a2 + 8);
          *((_DWORD *)v5 + 10) = *((_DWORD *)a2 + 10);
          *((_DWORD *)v5 + 9) = *((_DWORD *)a2 + 9);
          *((_DWORD *)v5 + 11) = *((_DWORD *)a2 + 11);
          v7 = *((_QWORD *)a2 + 6);
          if ( v7 )
          {
            *((_QWORD *)v5 + 6) = v7;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
          }
          *v4 = (__int64)v5;
        }
        else
        {
          v6 = -2147024882;
        }
      }
      else
      {
        v6 = -2147024809;
      }
      if ( (xmmword_180107A60 & 0x20) != 0 )
        WPP_SF_d(1029, 12, WPP_23d61de28852329ea54c9edce07bfeba_Traceguids, v6, v9);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  }
  else
  {
    v6 = -2147024809;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 23, WPP_8f662043cd0431ebe0ccb29223685825_Traceguids, v6, v9);
  return v6;
}

```

## disassembly

```asm
0x180071ae0  mov     [rsp+arg_10], rbx
0x180071ae5  push    rbp
0x180071ae6  push    rsi
0x180071ae7  push    rdi
0x180071ae8  push    r13
0x180071aea  push    r14
0x180071aec  sub     rsp, 40h
0x180071af0  mov     r14, rdx
0x180071af3  mov     [rsp+68h+var_34], 0
0x180071afb  mov     rbp, rcx
0x180071afe  test    byte ptr cs:xmmword_180107A60, 20h
0x180071b05  lea     rsi, [rcx+0F0h]
0x180071b0c  mov     r13d, 405h
0x180071b12  jnz     loc_180071C90
0x180071b18  test    r14, r14
0x180071b1b  jz      loc_180071CB4
0x180071b21  lea     rcx, [rbp+98h]; lpCriticalSection
0x180071b28  call    cs:__imp_EnterCriticalSection
0x180071b2e  cmp     qword ptr [rsi], 0
0x180071b32  jnz     loc_180071D1C
0x180071b38  mov     [rsp+68h+var_34], 0
0x180071b40  test    byte ptr cs:xmmword_180107A60, 20h
0x180071b47  jnz     loc_180071CFB
0x180071b4d  test    rsi, rsi
0x180071b50  jz      loc_180071CD4
0x180071b56  mov     qword ptr [rsi], 0
0x180071b5d  mov     ecx, 38h ; '8'; cb
0x180071b62  mov     [rsp+68h+var_34], 0
0x180071b6a  call    cs:__imp_CoTaskMemAlloc
0x180071b70  mov     rbx, rax
0x180071b73  test    rax, rax
0x180071b76  jz      loc_180071D2E
0x180071b7c  xorps   xmm0, xmm0
0x180071b7f  xor     eax, eax
0x180071b81  movups  xmmword ptr [rbx], xmm0
0x180071b84  movups  xmmword ptr [rbx+10h], xmm0
0x180071b88  movups  xmmword ptr [rbx+20h], xmm0
0x180071b8c  mov     [rbx+30h], rax
0x180071b90  mov     [rsp+68h+var_34], eax
0x180071b94  test    byte ptr cs:xmmword_180107A60, 20h
0x180071b9b  jnz     loc_180071D48
0x180071ba1  mov     eax, [r14]
0x180071ba4  xor     edi, edi
0x180071ba6  mov     [rbx], eax
0x180071ba8  mov     eax, [r14+4]
0x180071bac  mov     [rbx+4], eax
0x180071baf  mov     eax, [r14+8]
0x180071bb3  mov     [rbx+8], eax
0x180071bb6  mov     eax, [r14+14h]
0x180071bba  mov     [rbx+14h], eax
0x180071bbd  mov     eax, [r14+0Ch]
0x180071bc1  mov     [rbx+0Ch], eax
0x180071bc4  mov     eax, [r14+10h]
0x180071bc8  mov     [rbx+10h], eax
0x180071bcb  mov     eax, [r14+18h]
0x180071bcf  mov     [rbx+18h], eax
0x180071bd2  mov     eax, [r14+1Ch]
0x180071bd6  mov     [rbx+1Ch], eax
0x180071bd9  mov     eax, [r14+20h]
0x180071bdd  mov     [rbx+20h], eax
0x180071be0  mov     eax, [r14+28h]
0x180071be4  mov     [rbx+28h], eax
0x180071be7  mov     eax, [r14+24h]
0x180071beb  mov     [rbx+24h], eax
0x180071bee  mov     eax, [r14+2Ch]
0x180071bf2  mov     [rbx+2Ch], eax
0x180071bf5  mov     rcx, [r14+30h]
0x180071bf9  test    rcx, rcx
0x180071bfc  jnz     loc_180071CE6
0x180071c02  mov     [rsi], rbx
0x180071c05  xor     ebx, ebx
0x180071c07  test    byte ptr cs:xmmword_180107A60, 20h
0x180071c0e  jnz     loc_180071D69
0x180071c14  test    rbx, rbx
0x180071c17  jz      short loc_180071C43
0x180071c19  mov     rcx, [rbx+30h]
0x180071c1d  test    rcx, rcx
0x180071c20  jnz     loc_180071CC3
0x180071c26  xorps   xmm0, xmm0
0x180071c29  xor     eax, eax
0x180071c2b  movups  xmmword ptr [rbx], xmm0
0x180071c2e  movups  xmmword ptr [rbx+10h], xmm0
0x180071c32  movups  xmmword ptr [rbx+20h], xmm0
0x180071c36  mov     [rbx+30h], rax
0x180071c3a  mov     rcx, rbx; pv
0x180071c3d  call    cs:__imp_CoTaskMemFree
0x180071c43  test    edi, edi
0x180071c45  js      loc_180071D85
0x180071c4b  lea     rcx, [rbp+98h]; lpCriticalSection
0x180071c52  call    cs:__imp_LeaveCriticalSection
0x180071c58  test    byte ptr cs:xmmword_180107A60, 20h
0x180071c5f  jnz     short loc_180071C77
0x180071c61  mov     rbx, [rsp+68h+arg_10]
0x180071c69  mov     eax, edi
0x180071c6b  add     rsp, 40h
0x180071c6f  pop     r14
0x180071c71  pop     r13
0x180071c73  pop     rdi
0x180071c74  pop     rsi
0x180071c75  pop     rbp
0x180071c76  retn
0x180071c77  mov     edx, 17h
0x180071c7c  lea     r8, WPP_8f662043cd0431ebe0ccb29223685825_Traceguids
0x180071c83  mov     ecx, r13d
0x180071c86  mov     r9d, edi
0x180071c89  call    WPP_SF_d
0x180071c8e  jmp     short loc_180071C61
0x180071c90  mov     rax, [rsi]
0x180071c93  lea     r8, WPP_8f662043cd0431ebe0ccb29223685825_Traceguids
0x180071c9a  mov     edx, 16h
0x180071c9f  mov     [rsp+68h+var_48], rax
0x180071ca4  mov     ecx, r13d
0x180071ca7  mov     r9, r14
0x180071caa  call    WPP_SF_qq
0x180071caf  jmp     loc_180071B18
0x180071cb4  mov     edi, 80070057h
0x180071cb9  mov     [rsp+68h+var_34], 363h
0x180071cc1  jmp     short loc_180071C58
0x180071cc3  mov     rax, [rcx]
0x180071cc6  mov     rax, [rax+10h]
0x180071cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ccf  jmp     loc_180071C26
0x180071cd4  mov     edi, 80070057h
0x180071cd9  mov     [rsp+68h+var_34], 148h
0x180071ce1  jmp     loc_180071C05
0x180071ce6  mov     [rbx+30h], rcx
0x180071cea  mov     rax, [rcx]
0x180071ced  mov     rax, [rax+8]
0x180071cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071cf6  jmp     loc_180071C02
0x180071cfb  mov     edx, 0Bh
0x180071d00  mov     [rsp+68h+var_48], rsi
0x180071d05  mov     ecx, r13d
0x180071d08  lea     r8, WPP_23d61de28852329ea54c9edce07bfeba_Traceguids
0x180071d0f  mov     r9, r14
0x180071d12  call    WPP_SF_qq
0x180071d17  jmp     loc_180071B4D
0x180071d1c  mov     edi, 80070057h
0x180071d21  mov     [rsp+68h+var_34], 36Ch
0x180071d29  jmp     loc_180071C4B
0x180071d2e  mov     [rsp+68h+var_34], 4Ch ; 'L'
0x180071d36  mov     edi, 8007000Eh
0x180071d3b  mov     [rsp+68h+var_34], 14Eh
0x180071d43  jmp     loc_180071C05
0x180071d48  mov     edx, 0Ah
0x180071d4d  mov     [rsp+68h+var_48], rbx
0x180071d52  mov     ecx, r13d
0x180071d55  lea     r8, WPP_23d61de28852329ea54c9edce07bfeba_Traceguids
0x180071d5c  mov     r9, r14
0x180071d5f  call    WPP_SF_qq
0x180071d64  jmp     loc_180071BA1
0x180071d69  mov     edx, 0Ch
0x180071d6e  lea     r8, WPP_23d61de28852329ea54c9edce07bfeba_Traceguids
0x180071d75  mov     ecx, r13d
0x180071d78  mov     r9d, edi
0x180071d7b  call    WPP_SF_d
0x180071d80  jmp     loc_180071C14
0x180071d85  mov     [rsp+68h+var_34], 36Dh
0x180071d8d  jmp     loc_180071C4B
```
