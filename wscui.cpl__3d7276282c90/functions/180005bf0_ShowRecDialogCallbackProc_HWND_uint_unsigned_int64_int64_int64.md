# ShowRecDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x180005bf0`
- end: `0x180005ceb`
- name: `?ShowRecDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `251`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005bf0`
- `0x180006520`
- `0x180008930`
- `0x180009d08`
- `0x180009dfc`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180005cda`
- `ntdll!EtwEventWrite` at `0x180005cda`
- `USER32!SendMessageW` at `0x180005cb9`
- `USER32!SendMessageW` at `0x180005cb9`

## pseudocode

```c
_BOOL8 __fastcall ShowRecDialogCallbackProc(HWND a1, int a2, unsigned int a3, __int64 a4, __int64 *a5)
{
  __int64 v7; // rdi
  unsigned int v8; // edx
  OLECHAR *v9; // rdx
  __int64 v11; // rdi
  __int64 v12; // rax
  UINT v13; // edx
  LPARAM v14; // r9

  v7 = *a5;
  if ( !a2 )
  {
    v11 = 0;
    if ( !*((_DWORD *)a5 + 4) )
    {
LABEL_22:
      EtwEventWrite(g_Provider, &WSC_UI_LaunchDialog_End, 0, 0);
      return 0;
    }
    while ( *(_DWORD *)(a5[1] + 8 * v11) != 102 && (unsigned int)(*(_DWORD *)(a5[1] + 8 * v11) - 117) > 1
         || (unsigned int)RunningAsAdministrator() )
    {
      v12 = a5[1];
      if ( *(_DWORD *)(v12 + 8 * v11) == 100 )
      {
        v14 = 0;
        v13 = 1135;
        goto LABEL_20;
      }
LABEL_21:
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= *((_DWORD *)a5 + 4) )
        goto LABEL_22;
    }
    v12 = a5[1];
    v13 = 1139;
    v14 = 1;
LABEL_20:
    SendMessageW(a1, v13, *(int *)(v12 + 8 * v11), v14);
    goto LABEL_21;
  }
  v8 = a2 - 2;
  if ( v8 )
  {
    if ( v8 == 1 )
    {
      v9 = 0;
      if ( *(_DWORD *)(v7 + 8) == 1 || *(_DWORD *)(v7 + 8) == 3 || *(_DWORD *)(v7 + 8) == 4 || *(_DWORD *)(v7 + 8) == 6 )
        v9 = (OLECHAR *)L"mshelp://windows/?id=1154af45-f28e-4de4-949d-bc5fa8d204a8";
      LaunchURL(a1, v9);
      goto LABEL_10;
    }
    return 0;
  }
LABEL_10:
  if ( *(_DWORD *)(v7 + 56) == 109 )
    SendUNPSqm(a3, v8, a3);
  return ExecuteSecurityActionHandler(a1, a3, (struct SecurityLogicState *)v7, 0) == 0;
}

```

## disassembly

```asm
0x180005bf0  push    rbx
0x180005bf2  push    rbp
0x180005bf3  push    rsi
0x180005bf4  push    rdi
0x180005bf5  sub     rsp, 28h
0x180005bf9  mov     rbx, [rsp+48h+arg_20]
0x180005bfe  mov     rsi, r8
0x180005c01  mov     rbp, rcx
0x180005c04  mov     rdi, [rbx]
0x180005c07  test    edx, edx
0x180005c09  jz      short loc_180005C69
0x180005c0b  sub     edx, 2
0x180005c0e  jz      short loc_180005C41
0x180005c10  cmp     edx, 1
0x180005c13  jnz     loc_180005CE0
0x180005c19  mov     ecx, [rdi+8]
0x180005c1c  xor     edx, edx
0x180005c1e  sub     ecx, 1
0x180005c21  jz      short loc_180005C32
0x180005c23  sub     ecx, 2
0x180005c26  jz      short loc_180005C32
0x180005c28  sub     ecx, 1
0x180005c2b  jz      short loc_180005C32
0x180005c2d  cmp     ecx, 2
0x180005c30  jnz     short loc_180005C39
0x180005c32  lea     rdx, psz; "mshelp://windows/?id=1154af45-f28e-4de4"...
0x180005c39  mov     rcx, rbp; HWND
0x180005c3c  call    ?LaunchURL@@YA_NPEAUHWND__@@PEBG@Z; LaunchURL(HWND__ *,ushort const *)
0x180005c41  cmp     dword ptr [rdi+38h], 6Dh ; 'm'
0x180005c45  jnz     short loc_180005C4E
0x180005c47  mov     ecx, esi; unsigned int
0x180005c49  call    ?SendUNPSqm@@YAXKKH@Z; SendUNPSqm(ulong,ulong,int)
0x180005c4e  xor     r9d, r9d
0x180005c51  mov     r8, rdi
0x180005c54  mov     edx, esi
0x180005c56  mov     rcx, rbp
0x180005c59  call    ?ExecuteSecurityActionHandler@@YA_NPEAUHWND__@@W4SecurityAction@@PEAVSecurityLogicState@@_N@Z; ExecuteSecurityActionHandler(HWND__ *,SecurityAction,SecurityLogicState *,bool)
0x180005c5e  xor     ecx, ecx
0x180005c60  test    al, al
0x180005c62  setz    cl
0x180005c65  mov     eax, ecx
0x180005c67  jmp     short loc_180005CE2
0x180005c69  xor     edi, edi
0x180005c6b  cmp     [rbx+10h], edi
0x180005c6e  jbe     short loc_180005CC6
0x180005c70  mov     rcx, [rbx+8]
0x180005c74  mov     edx, [rcx+rdi*8]
0x180005c77  sub     edx, 66h ; 'f'
0x180005c7a  jz      short loc_180005C86
0x180005c7c  sub     edx, 0Fh
0x180005c7f  jz      short loc_180005C86
0x180005c81  cmp     edx, 1
0x180005c84  jnz     short loc_180005CA0
0x180005c86  call    RunningAsAdministrator
0x180005c8b  test    eax, eax
0x180005c8d  jnz     short loc_180005CA0
0x180005c8f  mov     rax, [rbx+8]
0x180005c93  mov     edx, 473h
0x180005c98  mov     r9d, 1
0x180005c9e  jmp     short loc_180005CB2
0x180005ca0  mov     rax, [rbx+8]
0x180005ca4  cmp     dword ptr [rax+rdi*8], 64h ; 'd'
0x180005ca8  jnz     short loc_180005CBF
0x180005caa  xor     r9d, r9d; lParam
0x180005cad  mov     edx, 46Fh; Msg
0x180005cb2  movsxd  r8, dword ptr [rax+rdi*8]; wParam
0x180005cb6  mov     rcx, rbp; hWnd
0x180005cb9  call    cs:__imp_SendMessageW
0x180005cbf  inc     edi
0x180005cc1  cmp     edi, [rbx+10h]
0x180005cc4  jb      short loc_180005C70
0x180005cc6  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x180005ccd  lea     rdx, WSC_UI_LaunchDialog_End
0x180005cd4  xor     r9d, r9d
0x180005cd7  xor     r8d, r8d
0x180005cda  call    cs:__imp_EtwEventWrite
0x180005ce0  xor     eax, eax
0x180005ce2  add     rsp, 28h
0x180005ce6  pop     rdi
0x180005ce7  pop     rsi
0x180005ce8  pop     rbp
0x180005ce9  pop     rbx
0x180005cea  retn
```
