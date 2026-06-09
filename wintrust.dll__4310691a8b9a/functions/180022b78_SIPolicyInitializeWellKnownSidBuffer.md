# SIPolicyInitializeWellKnownSidBuffer

- ea: `0x180022b78`
- end: `0x180022e07`
- name: `SIPolicyInitializeWellKnownSidBuffer`
- size: `655`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180041e8c`
- `0x180043f70`

## callees

- `0x180022b78`
- `0x18004deb0`

## import_xrefs

- `ntdll!RtlInitializeSidEx` at `0x180022bce`
- `ntdll!RtlInitializeSidEx` at `0x180022bf1`
- `ntdll!RtlInitializeSidEx` at `0x180022c11`
- `ntdll!RtlInitializeSidEx` at `0x180022c31`
- `ntdll!RtlInitializeSidEx` at `0x180022c5b`
- `ntdll!RtlInitializeSidEx` at `0x180022c82`
- `ntdll!RtlInitializeSidEx` at `0x180022ca9`
- `ntdll!RtlInitializeSidEx` at `0x180022ccc`
- `ntdll!RtlInitializeSidEx` at `0x180022cef`
- `ntdll!RtlInitializeSidEx` at `0x180022d12`
- `ntdll!RtlInitializeSidEx` at `0x180022d4d`
- `ntdll!RtlInitializeSidEx` at `0x180022da5`
- `ntdll!RtlInitializeSidEx` at `0x180022dfc`
- `ntdll!RtlInitializeSidEx` at `0x180022bce`
- `ntdll!RtlInitializeSidEx` at `0x180022bf1`
- `ntdll!RtlInitializeSidEx` at `0x180022c11`
- `ntdll!RtlInitializeSidEx` at `0x180022c31`
- `ntdll!RtlInitializeSidEx` at `0x180022c5b`
- `ntdll!RtlInitializeSidEx` at `0x180022c82`
- `ntdll!RtlInitializeSidEx` at `0x180022ca9`
- `ntdll!RtlInitializeSidEx` at `0x180022ccc`
- `ntdll!RtlInitializeSidEx` at `0x180022cef`
- `ntdll!RtlInitializeSidEx` at `0x180022d12`
- `ntdll!RtlInitializeSidEx` at `0x180022d4d`
- `ntdll!RtlInitializeSidEx` at `0x180022da5`
- `ntdll!RtlInitializeSidEx` at `0x180022dfc`

## pseudocode

```c
__int64 SIPolicyInitializeWellKnownSidBuffer()
{
  __int64 result; // rax
  __int64 v1; // [rsp+20h] [rbp-29h]
  __int64 v2; // [rsp+20h] [rbp-29h]
  __int64 v3; // [rsp+20h] [rbp-29h]
  __int64 v4; // [rsp+20h] [rbp-29h]
  __int64 v5; // [rsp+20h] [rbp-29h]
  __int64 v6; // [rsp+20h] [rbp-29h]
  __int64 v7; // [rsp+20h] [rbp-29h]
  __int64 v8; // [rsp+20h] [rbp-29h]
  __int64 v9; // [rsp+20h] [rbp-29h]
  __int64 v10; // [rsp+20h] [rbp-29h]
  __int64 v11; // [rsp+20h] [rbp-29h]
  __int64 v12; // [rsp+20h] [rbp-29h]
  int v13; // [rsp+60h] [rbp+17h] BYREF
  __int16 v14; // [rsp+64h] [rbp+1Bh]
  int v15; // [rsp+68h] [rbp+1Fh] BYREF
  __int16 v16; // [rsp+6Ch] [rbp+23h]
  int v17; // [rsp+70h] [rbp+27h] BYREF
  __int16 v18; // [rsp+74h] [rbp+2Bh]

  v18 = 768;
  v17 = 0;
  v13 = 0;
  v14 = 1280;
  v15 = 0;
  v16 = 3840;
  result = RtlInitializeSidEx(g_SIPolicyWellKnownSids, &v17, 2, 3, 0);
  if ( (int)result >= 0 )
  {
    result = RtlInitializeSidEx(&dword_18006A384, &v13, 1, 18, v1);
    if ( (int)result >= 0 )
    {
      result = RtlInitializeSidEx(qword_18006A3C8, &v13, 1, 19, v2);
      if ( (int)result >= 0 )
      {
        result = RtlInitializeSidEx(&dword_18006A40C, &v13, 1, 20, v3);
        if ( (int)result >= 0 )
        {
          LODWORD(v4) = 544;
          result = RtlInitializeSidEx(qword_18006A450, &v13, 2, 32, v4);
          if ( (int)result >= 0 )
          {
            LODWORD(v5) = 594;
            result = RtlInitializeSidEx(&dword_18006A494, &v13, 2, 32, v5);
            if ( (int)result >= 0 )
            {
              LODWORD(v6) = 550;
              result = RtlInitializeSidEx(qword_18006A4D8, &v13, 2, 32, v6);
              if ( (int)result >= 0 )
              {
                LODWORD(v7) = 551;
                result = RtlInitializeSidEx(&dword_18006A51C, &v13, 2, 32, v7);
                if ( (int)result >= 0 )
                {
                  LODWORD(v8) = 577;
                  result = RtlInitializeSidEx(qword_18006A560, &v13, 2, 32, v8);
                  if ( (int)result >= 0 )
                  {
                    LODWORD(v9) = 559;
                    result = RtlInitializeSidEx(&dword_18006A5A4, &v13, 2, 32, v9);
                    if ( (int)result >= 0 )
                    {
                      LODWORD(v10) = 568;
                      result = RtlInitializeSidEx(qword_18006A5E8, &v13, 2, 32, v10);
                      if ( (int)result >= 0 )
                      {
                        LODWORD(v11) = 1430448594;
                        result = RtlInitializeSidEx(&dword_18006A62C, &v15, 8, 2, v11);
                        if ( (int)result >= 0 )
                        {
                          LODWORD(v12) = 95739096;
                          return RtlInitializeSidEx(qword_18006A670, &v15, 8, 2, v12);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180022b78  push    rbp
0x180022b7a  push    rbx
0x180022b7b  push    rsi
0x180022b7c  push    rdi
0x180022b7d  lea     rbp, [rsp-3Fh]
0x180022b82  sub     rsp, 88h
0x180022b89  mov     rax, cs:__security_cookie
0x180022b90  xor     rax, rsp
0x180022b93  mov     [rbp+57h+var_28], rax
0x180022b97  xor     ebx, ebx
0x180022b99  mov     [rbp+57h+var_2C], 300h
0x180022b9f  lea     rdx, [rbp+57h+var_30]
0x180022ba3  mov     [rbp+57h+var_30], ebx
0x180022ba6  lea     rcx, g_SIPolicyWellKnownSids
0x180022bad  mov     [rbp+57h+var_40], ebx
0x180022bb0  mov     [rbp+57h+var_3C], 500h
0x180022bb6  lea     edi, [rbx+2]
0x180022bb9  mov     [rbp+57h+var_38], ebx
0x180022bbc  mov     r8d, edi
0x180022bbf  mov     [rbp+57h+var_34], 0F00h
0x180022bc5  lea     r9d, [rbx+3]
0x180022bc9  mov     [rsp+0A0h+var_80], rbx
0x180022bce  call    cs:__imp_RtlInitializeSidEx
0x180022bd4  test    eax, eax
0x180022bd6  js      loc_180022D1C
0x180022bdc  lea     esi, [rbx+1]
0x180022bdf  mov     r8d, esi
0x180022be2  lea     r9d, [rbx+12h]
0x180022be6  lea     rdx, [rbp+57h+var_40]
0x180022bea  lea     rcx, dword_18006A384
0x180022bf1  call    cs:__imp_RtlInitializeSidEx
0x180022bf7  test    eax, eax
0x180022bf9  js      loc_180022D1C
0x180022bff  lea     r9d, [rbx+13h]
0x180022c03  mov     r8d, esi
0x180022c06  lea     rdx, [rbp+57h+var_40]
0x180022c0a  lea     rcx, qword_18006A3C8
0x180022c11  call    cs:__imp_RtlInitializeSidEx
0x180022c17  test    eax, eax
0x180022c19  js      loc_180022D1C
0x180022c1f  lea     r9d, [rbx+14h]
0x180022c23  mov     r8d, esi
0x180022c26  lea     rdx, [rbp+57h+var_40]
0x180022c2a  lea     rcx, dword_18006A40C
0x180022c31  call    cs:__imp_RtlInitializeSidEx
0x180022c37  test    eax, eax
0x180022c39  js      loc_180022D1C
0x180022c3f  lea     esi, [rbx+20h]
0x180022c42  mov     dword ptr [rsp+0A0h+var_80], 220h
0x180022c4a  mov     r9d, esi
0x180022c4d  lea     rdx, [rbp+57h+var_40]
0x180022c51  mov     r8d, edi
0x180022c54  lea     rcx, qword_18006A450
0x180022c5b  call    cs:__imp_RtlInitializeSidEx
0x180022c61  test    eax, eax
0x180022c63  js      loc_180022D1C
0x180022c69  mov     r9d, esi
0x180022c6c  mov     dword ptr [rsp+0A0h+var_80], 252h
0x180022c74  mov     r8d, edi
0x180022c77  lea     rdx, [rbp+57h+var_40]
0x180022c7b  lea     rcx, dword_18006A494
0x180022c82  call    cs:__imp_RtlInitializeSidEx
0x180022c88  test    eax, eax
0x180022c8a  js      loc_180022D1C
0x180022c90  mov     r9d, esi
0x180022c93  mov     dword ptr [rsp+0A0h+var_80], 226h
0x180022c9b  mov     r8d, edi
0x180022c9e  lea     rdx, [rbp+57h+var_40]
0x180022ca2  lea     rcx, qword_18006A4D8
0x180022ca9  call    cs:__imp_RtlInitializeSidEx
0x180022caf  test    eax, eax
0x180022cb1  js      short loc_180022D1C
0x180022cb3  mov     r9d, esi
0x180022cb6  mov     dword ptr [rsp+0A0h+var_80], 227h
0x180022cbe  mov     r8d, edi
0x180022cc1  lea     rdx, [rbp+57h+var_40]
0x180022cc5  lea     rcx, dword_18006A51C
0x180022ccc  call    cs:__imp_RtlInitializeSidEx
0x180022cd2  test    eax, eax
0x180022cd4  js      short loc_180022D1C
0x180022cd6  mov     r9d, esi
0x180022cd9  mov     dword ptr [rsp+0A0h+var_80], 241h
0x180022ce1  mov     r8d, edi
0x180022ce4  lea     rdx, [rbp+57h+var_40]
0x180022ce8  lea     rcx, qword_18006A560
0x180022cef  call    cs:__imp_RtlInitializeSidEx
0x180022cf5  test    eax, eax
0x180022cf7  js      short loc_180022D1C
0x180022cf9  mov     r9d, esi
0x180022cfc  mov     dword ptr [rsp+0A0h+var_80], 22Fh
0x180022d04  mov     r8d, edi
0x180022d07  lea     rdx, [rbp+57h+var_40]
0x180022d0b  lea     rcx, dword_18006A5A4
0x180022d12  call    cs:__imp_RtlInitializeSidEx
0x180022d18  test    eax, eax
0x180022d1a  jns     short loc_180022D34
0x180022d1c  mov     rcx, [rbp+57h+var_28]
0x180022d20  xor     rcx, rsp; StackCookie
0x180022d23  call    __security_check_cookie
0x180022d28  add     rsp, 88h
0x180022d2f  pop     rdi
0x180022d30  pop     rsi
0x180022d31  pop     rbx
0x180022d32  pop     rbp
0x180022d33  retn
0x180022d34  mov     r9d, esi
0x180022d37  mov     dword ptr [rsp+0A0h+var_80], 238h
0x180022d3f  mov     r8d, edi
0x180022d42  lea     rdx, [rbp+57h+var_40]
0x180022d46  lea     rcx, qword_18006A5E8
0x180022d4d  call    cs:__imp_RtlInitializeSidEx
0x180022d53  test    eax, eax
0x180022d55  js      short loc_180022D1C
0x180022d57  mov     [rsp+0A0h+var_50], 4C2B8C5Ah
0x180022d5f  lea     rdx, [rbp+57h+var_38]
0x180022d63  mov     [rsp+0A0h+var_58], 0F28A92BCh
0x180022d6b  lea     rcx, dword_18006A62C
0x180022d72  mov     [rsp+0A0h+var_60], 4767CC4Fh
0x180022d7a  mov     esi, 8
0x180022d7f  mov     [rsp+0A0h+var_68], 1A2FA379h
0x180022d87  mov     r9d, edi
0x180022d8a  mov     [rsp+0A0h+var_70], 3A0B3827h
0x180022d92  mov     r8d, esi
0x180022d95  mov     [rsp+0A0h+var_78], 9D4F738Eh
0x180022d9d  mov     dword ptr [rsp+0A0h+var_80], 5542E9D2h
0x180022da5  call    cs:__imp_RtlInitializeSidEx
0x180022dab  test    eax, eax
0x180022dad  js      loc_180022D1C
0x180022db3  mov     [rsp+0A0h+var_50], 0A3B6F52Bh
0x180022dbb  lea     rdx, [rbp+57h+var_38]
0x180022dbf  mov     [rsp+0A0h+var_58], 1A7CAEBBh
0x180022dc7  lea     rcx, qword_18006A670
0x180022dce  mov     [rsp+0A0h+var_60], 64782BBFh
0x180022dd6  mov     r9d, edi
0x180022dd9  mov     [rsp+0A0h+var_68], 0E5B1155Bh
0x180022de1  mov     r8d, esi
0x180022de4  mov     [rsp+0A0h+var_70], 79318273h
0x180022dec  mov     [rsp+0A0h+var_78], 1D02DE5Ch
0x180022df4  mov     dword ptr [rsp+0A0h+var_80], 5B4DCD8h
0x180022dfc  call    cs:__imp_RtlInitializeSidEx
0x180022e02  jmp     loc_180022D1C
```
