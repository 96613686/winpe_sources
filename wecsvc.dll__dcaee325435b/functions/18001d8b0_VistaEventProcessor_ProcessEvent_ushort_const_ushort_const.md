# VistaEventProcessor::ProcessEvent(ushort const *,ushort const *)

- ea: `0x18001d8b0`
- end: `0x18001da46`
- name: `?ProcessEvent@VistaEventProcessor@@UEAAXPEBG0@Z`
- size: `406`
- prototype: `void __fastcall(VistaEventProcessor *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001d8b0`
- `0x18001da4c`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d987`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d987`
- `ntdll!EtwEventWriteFull` at `0x18001d93d`
- `ntdll!EtwEventWriteFull` at `0x18001d93d`

## pseudocode

```c
void __fastcall VistaEventProcessor::ProcessEvent(
        VistaEventProcessor *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v3; // rax
  char v5; // al
  DWORD v6; // ebx
  unsigned int v7; // esi
  unsigned int v8; // edi
  void **pExceptionObject; // [rsp+40h] [rbp-39h] BYREF
  char v10; // [rsp+48h] [rbp-31h]
  const char *v11; // [rsp+50h] [rbp-29h]
  __int64 v12; // [rsp+58h] [rbp-21h]
  __int64 v13; // [rsp+60h] [rbp-19h]
  unsigned int v14; // [rsp+68h] [rbp-11h]
  int v15; // [rsp+6Ch] [rbp-Dh]
  int v16; // [rsp+70h] [rbp-9h]
  const unsigned __int16 *v17; // [rsp+78h] [rbp-1h] BYREF
  int v18; // [rsp+80h] [rbp+7h]
  int v19; // [rsp+84h] [rbp+Bh]
  __int128 v20; // [rsp+88h] [rbp+Fh] BYREF

  v3 = -1;
  v17 = a3;
  do
    ++v3;
  while ( a3[v3] );
  v19 = 0;
  v18 = 2 * v3 + 2;
  v5 = *((_BYTE *)this + 80);
  v6 = 1;
  v20 = 0;
  BYTE3(v20) = v5;
  v7 = 0;
  *((_QWORD *)&v20 + 1) = *((_QWORD *)this + 13);
  do
  {
    v8 = EtwEventWriteFull(*((_QWORD *)this + 14), &v20, 2, 0, 0, 1, &v17);
    if ( v8 != 8 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8 + 7, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, v6, v7);
    }
    v7 += v6;
    Sleep(v6);
    if ( v6 >= 0x1F4 )
      v6 = 500;
    else
      v6 += 16;
  }
  while ( v7 < 0x4E20 );
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, v8);
    }
    v10 = 0;
    v11 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
    v12 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v13 = 0;
    v14 = v8;
    v15 = -1;
    v16 = 167;
    throw (wmi::GenericException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18001d8b0  push    rbp
0x18001d8b2  push    rbx
0x18001d8b3  push    rsi
0x18001d8b4  push    rdi
0x18001d8b5  push    r14
0x18001d8b7  push    r15
0x18001d8b9  lea     rbp, [rsp-2Fh]
0x18001d8be  sub     rsp, 0A8h
0x18001d8c5  mov     rax, cs:__security_cookie
0x18001d8cc  xor     rax, rsp
0x18001d8cf  mov     [rbp+57h+var_38], rax
0x18001d8d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d8d7  mov     [rbp+57h+var_58], r8
0x18001d8db  xor     r15d, r15d
0x18001d8de  mov     r14, rcx
0x18001d8e1  inc     rax
0x18001d8e4  cmp     [r8+rax*2], r15w
0x18001d8e9  jnz     short loc_18001D8E1
0x18001d8eb  lea     eax, ds:2[rax*2]
0x18001d8f2  mov     [rbp+57h+var_4C], r15d
0x18001d8f6  mov     [rbp+57h+var_50], eax
0x18001d8f9  xorps   xmm0, xmm0
0x18001d8fc  mov     al, [rcx+50h]
0x18001d8ff  mov     ebx, 1
0x18001d904  movups  [rbp+57h+var_48], xmm0
0x18001d908  mov     byte ptr [rbp+57h+var_48+3], al
0x18001d90b  mov     esi, r15d
0x18001d90e  mov     rax, [rcx+68h]
0x18001d912  mov     qword ptr [rbp+57h+var_48+8], rax
0x18001d916  mov     rcx, [r14+70h]
0x18001d91a  lea     rax, [rbp+57h+var_58]
0x18001d91e  mov     [rsp+0D0h+var_A0], rax
0x18001d923  lea     rdx, [rbp+57h+var_48]
0x18001d927  mov     [rsp+0D0h+var_A8], 1
0x18001d92f  mov     r8d, 2
0x18001d935  xor     r9d, r9d
0x18001d938  mov     [rsp+0D0h+var_B0], r15
0x18001d93d  call    cs:__imp_EtwEventWriteFull
0x18001d943  mov     edi, eax
0x18001d945  cmp     eax, 8
0x18001d948  jnz     short loc_18001D9AB
0x18001d94a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d951  lea     rax, WPP_GLOBAL_Control
0x18001d958  cmp     rcx, rax
0x18001d95b  jz      short loc_18001D983
0x18001d95d  test    byte ptr [rcx+1Ch], 10h
0x18001d961  jz      short loc_18001D983
0x18001d963  cmp     byte ptr [rcx+19h], 5
0x18001d967  jb      short loc_18001D983
0x18001d969  mov     rcx, [rcx+10h]
0x18001d96d  lea     edx, [rdi+7]
0x18001d970  mov     r9d, ebx
0x18001d973  mov     dword ptr [rsp+0D0h+var_B0], esi
0x18001d977  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001d97e  call    WPP_SF_dd
0x18001d983  mov     ecx, ebx; dwMilliseconds
0x18001d985  add     esi, ebx
0x18001d987  call    cs:__imp_Sleep
0x18001d98d  cmp     ebx, 1F4h
0x18001d993  jnb     short loc_18001D99A
0x18001d995  add     ebx, 10h
0x18001d998  jmp     short loc_18001D99F
0x18001d99a  mov     ebx, 1F4h
0x18001d99f  cmp     esi, 4E20h
0x18001d9a5  jb      loc_18001D916
0x18001d9ab  test    edi, edi
0x18001d9ad  jz      short loc_18001DA2A
0x18001d9af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9b6  lea     rax, WPP_GLOBAL_Control
0x18001d9bd  cmp     rcx, rax
0x18001d9c0  jz      short loc_18001D9E6
0x18001d9c2  test    byte ptr [rcx+1Ch], 1
0x18001d9c6  jz      short loc_18001D9E6
0x18001d9c8  cmp     byte ptr [rcx+19h], 2
0x18001d9cc  jb      short loc_18001D9E6
0x18001d9ce  mov     rcx, [rcx+10h]
0x18001d9d2  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001d9d9  mov     edx, 10h
0x18001d9de  mov     r9d, edi
0x18001d9e1  call    WPP_SF_D
0x18001d9e6  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001d9ed  mov     [rbp+57h+var_88], r15b
0x18001d9f1  mov     [rbp+57h+var_80], rax
0x18001d9f5  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001d9fc  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001da03  mov     [rbp+57h+var_78], r15
0x18001da07  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001da0b  mov     [rbp+57h+pExceptionObject], rax
0x18001da0f  mov     [rbp+57h+var_70], r15
0x18001da13  mov     [rbp+57h+var_68], edi
0x18001da16  mov     [rbp+57h+var_64], 0FFFFFFFFh
0x18001da1d  mov     [rbp+57h+var_60], 0A7h
0x18001da24  call    _CxxThrowException_0
0x18001da2a  mov     rcx, [rbp+57h+var_38]
0x18001da2e  xor     rcx, rsp; StackCookie
0x18001da31  call    __security_check_cookie
0x18001da36  add     rsp, 0A8h
0x18001da3d  pop     r15
0x18001da3f  pop     r14
0x18001da41  pop     rdi
0x18001da42  pop     rsi
0x18001da43  pop     rbx
0x18001da44  pop     rbp
0x18001da45  retn
```
