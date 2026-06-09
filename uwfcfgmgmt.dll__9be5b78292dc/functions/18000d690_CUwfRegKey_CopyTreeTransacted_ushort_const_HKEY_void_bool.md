# CUwfRegKey::CopyTreeTransacted(ushort const *,HKEY__ *,void *,bool)

- ea: `0x18000d690`
- end: `0x18000d87d`
- name: `?CopyTreeTransacted@CUwfRegKey@@QEAAJPEBGPEAUHKEY__@@PEAX_N@Z`
- size: `493`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, HKEY, void *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006ae0`
- `0x18000d690`

## callees

- `0x18000d5a0`
- `0x18000d5f0`
- `0x18000d690`
- `0x18000d884`
- `0x18000db50`
- `0x18000dc40`
- `0x18000de30`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d7bd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d7bd`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::CopyTreeTransacted(HKEY *this, const unsigned __int16 *a2, HKEY a3, void *a4, bool a5)
{
  HKEY v6; // rsi
  LSTATUS v9; // eax
  signed int v10; // ebx
  DWORD i; // edi
  HKEY v12; // rcx
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v16[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  phkResult = 0;
  v6 = a3;
  cchName = 0;
  if ( a5 )
  {
    v16[0] = 0;
    CUwfRegKey::Attach((CUwfRegKey *)v16, a3);
    CUwfRegKey::DeleteTreeTransacted((CUwfRegKey *)v16, 0, a4);
    v6 = v16[0];
    v16[0] = 0;
    CUwfRegKey::Close(v16);
  }
  if ( a2 )
  {
    v9 = CUwfRegKey::Open(&phkResult, *this, a2, 0xF003Fu);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
LABEL_17:
        v10 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v9 = CUwfRegKey::CopyTreeTransacted((CUwfRegKey *)&phkResult, 0, v6, a4, a5);
LABEL_8:
      v10 = v9;
    }
  }
  else
  {
    v10 = CUwfRegKey::CopyValues((CUwfRegKey *)this, v6);
    if ( v10 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v12 = *this;
        cchName = 256;
        v9 = RegEnumKeyExW(v12, i, Name, &cchName, 0, 0, 0, 0);
        if ( v9 == 259 )
          break;
        if ( v9 )
        {
          if ( v9 <= 0 )
            goto LABEL_8;
          goto LABEL_17;
        }
        v10 = CUwfRegKey::CreateTransacted(&phkResult, v6, Name, 0, 0, 0xF003Fu, 0, 0, a4);
        if ( v10 < 0 )
          break;
        v10 = CUwfRegKey::CopyTreeTransacted((CUwfRegKey *)this, Name, phkResult, a4, a5);
        if ( v10 < 0 )
          break;
        CUwfRegKey::Close(&phkResult);
      }
    }
  }
  CUwfRegKey::Close(&phkResult);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000d690  push    rbp
0x18000d692  push    rbx
0x18000d693  push    rsi
0x18000d694  push    rdi
0x18000d695  push    r12
0x18000d697  push    r14
0x18000d699  push    r15
0x18000d69b  lea     rbp, [rsp-180h]
0x18000d6a3  sub     rsp, 280h
0x18000d6aa  mov     rax, cs:__security_cookie
0x18000d6b1  xor     rax, rsp
0x18000d6b4  mov     [rbp+1B0h+var_40], rax
0x18000d6bb  mov     r12b, [rbp+1B0h+arg_20]
0x18000d6c2  mov     r15, r9
0x18000d6c5  mov     [rsp+2B0h+phkResult], 0
0x18000d6ce  mov     rsi, r8
0x18000d6d1  mov     [rsp+2B0h+cchName], 0
0x18000d6d9  mov     rbx, rdx
0x18000d6dc  mov     r14, rcx
0x18000d6df  test    r12b, r12b
0x18000d6e2  jz      short loc_18000D721
0x18000d6e4  mov     rdx, r8; HKEY
0x18000d6e7  mov     [rsp+2B0h+var_250], 0
0x18000d6f0  lea     rcx, [rsp+2B0h+var_250]; this
0x18000d6f5  call    ?Attach@CUwfRegKey@@QEAAJPEAUHKEY__@@@Z; CUwfRegKey::Attach(HKEY__ *)
0x18000d6fa  mov     r8, r15; void *
0x18000d6fd  lea     rcx, [rsp+2B0h+var_250]; this
0x18000d702  xor     edx, edx; unsigned __int16 *
0x18000d704  call    ?DeleteTreeTransacted@CUwfRegKey@@QEAAJPEBGPEAX@Z; CUwfRegKey::DeleteTreeTransacted(ushort const *,void *)
0x18000d709  mov     rsi, [rsp+2B0h+var_250]
0x18000d70e  lea     rcx, [rsp+2B0h+var_250]; this
0x18000d713  mov     [rsp+2B0h+var_250], 0
0x18000d71c  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000d721  test    rbx, rbx
0x18000d724  jz      short loc_18000D76B
0x18000d726  mov     rdx, [r14]; hKey
0x18000d729  lea     rcx, [rsp+2B0h+phkResult]; phkResult
0x18000d72e  mov     r9d, 0F003Fh; samDesired
0x18000d734  mov     r8, rbx; lpSubKey
0x18000d737  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000d73c  mov     ebx, eax
0x18000d73e  test    eax, eax
0x18000d740  jz      short loc_18000D74D
0x18000d742  jle     loc_18000D850
0x18000d748  jmp     loc_18000D847
0x18000d74d  mov     r9, r15; void *
0x18000d750  mov     byte ptr [rsp+2B0h+lpReserved], r12b; bool
0x18000d755  mov     r8, rsi; HKEY
0x18000d758  lea     rcx, [rsp+2B0h+phkResult]; this
0x18000d75d  xor     edx, edx; unsigned __int16 *
0x18000d75f  call    ?CopyTreeTransacted@CUwfRegKey@@QEAAJPEBGPEAUHKEY__@@PEAX_N@Z; CUwfRegKey::CopyTreeTransacted(ushort const *,HKEY__ *,void *,bool)
0x18000d764  mov     ebx, eax
0x18000d766  jmp     loc_18000D850
0x18000d76b  mov     rdx, rsi; HKEY
0x18000d76e  mov     rcx, r14; this
0x18000d771  call    ?CopyValues@CUwfRegKey@@AEAAJPEAUHKEY__@@@Z; CUwfRegKey::CopyValues(HKEY__ *)
0x18000d776  mov     ebx, eax
0x18000d778  test    eax, eax
0x18000d77a  js      loc_18000D850
0x18000d780  xor     edi, edi
0x18000d782  mov     rcx, [r14]; hKey
0x18000d785  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18000d78a  mov     [rsp+2B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000d793  lea     r8, [rsp+2B0h+Name]; lpName
0x18000d798  mov     [rsp+2B0h+lpcchClass], 0; lpcchClass
0x18000d7a1  mov     edx, edi; dwIndex
0x18000d7a3  mov     [rsp+2B0h+lpClass], 0; lpClass
0x18000d7ac  mov     [rsp+2B0h+lpReserved], 0; lpReserved
0x18000d7b5  mov     [rsp+2B0h+cchName], 100h
0x18000d7bd  call    cs:__imp_RegEnumKeyExW
0x18000d7c3  cmp     eax, 103h
0x18000d7c8  jz      loc_18000D850
0x18000d7ce  test    eax, eax
0x18000d7d0  jnz     short loc_18000D841
0x18000d7d2  mov     [rsp+2B0h+var_270], r15; HANDLE
0x18000d7d7  lea     r8, [rsp+2B0h+Name]; lpSubKey
0x18000d7dc  mov     [rsp+2B0h+lpftLastWriteTime], 0; LPDWORD
0x18000d7e5  lea     rcx, [rsp+2B0h+phkResult]; phkResult
0x18000d7ea  mov     [rsp+2B0h+lpcchClass], 0; LPSECURITY_ATTRIBUTES
0x18000d7f3  xor     r9d, r9d; lpClass
0x18000d7f6  mov     dword ptr [rsp+2B0h+lpClass], 0F003Fh; REGSAM
0x18000d7fe  mov     rdx, rsi; hKey
0x18000d801  mov     dword ptr [rsp+2B0h+lpReserved], eax; DWORD
0x18000d805  call    ?CreateTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAKPEAX@Z; CUwfRegKey::CreateTransacted(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *,void *)
0x18000d80a  mov     ebx, eax
0x18000d80c  test    eax, eax
0x18000d80e  js      short loc_18000D850
0x18000d810  mov     r8, [rsp+2B0h+phkResult]; HKEY
0x18000d815  lea     rdx, [rsp+2B0h+Name]; unsigned __int16 *
0x18000d81a  mov     r9, r15; void *
0x18000d81d  mov     byte ptr [rsp+2B0h+lpReserved], r12b; bool
0x18000d822  mov     rcx, r14; this
0x18000d825  call    ?CopyTreeTransacted@CUwfRegKey@@QEAAJPEBGPEAUHKEY__@@PEAX_N@Z; CUwfRegKey::CopyTreeTransacted(ushort const *,HKEY__ *,void *,bool)
0x18000d82a  mov     ebx, eax
0x18000d82c  test    eax, eax
0x18000d82e  js      short loc_18000D850
0x18000d830  lea     rcx, [rsp+2B0h+phkResult]; this
0x18000d835  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000d83a  inc     edi
0x18000d83c  jmp     loc_18000D782
0x18000d841  jle     loc_18000D764
0x18000d847  movzx   ebx, ax
0x18000d84a  or      ebx, 80070000h
0x18000d850  lea     rcx, [rsp+2B0h+phkResult]; this
0x18000d855  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000d85a  mov     eax, ebx
0x18000d85c  mov     rcx, [rbp+1B0h+var_40]
0x18000d863  xor     rcx, rsp; StackCookie
0x18000d866  call    __security_check_cookie
0x18000d86b  add     rsp, 280h
0x18000d872  pop     r15
0x18000d874  pop     r14
0x18000d876  pop     r12
0x18000d878  pop     rdi
0x18000d879  pop     rsi
0x18000d87a  pop     rbx
0x18000d87b  pop     rbp
0x18000d87c  retn
```
