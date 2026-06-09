# EtwBlockingAppLog

- ea: `0x180006208`
- end: `0x18000639a`
- name: `EtwBlockingAppLog`
- size: `402`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008c10`

## callees

- `0x180006208`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000629e`
- `ntdll!NtQuerySystemInformation` at `0x18000629e`
- `ntdll!EtwEventWrite` at `0x18000636b`
- `ntdll!EtwEventWrite` at `0x18000636b`
- `USER32!GetWindowThreadProcessId` at `0x18000625a`
- `USER32!GetWindowThreadProcessId` at `0x18000625a`

## pseudocode

```c
void __fastcall EtwBlockingAppLog(int a1, HWND a2, int a3)
{
  __int16 v4; // r8
  _WORD *v5; // rcx
  _WORD *v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  __int64 v9; // r8
  __int64 *v10; // rdx
  DWORD dwProcessId; // [rsp+20h] [rbp-E0h] BYREF
  _WORD *SystemInformation; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+30h] [rbp-D0h]
  int *v14; // [rsp+38h] [rbp-C8h]
  __int64 v15; // [rsp+40h] [rbp-C0h]
  _WORD v16[264]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+2A0h] [rbp+1A0h] BYREF

  v17 = a3;
  if ( g_EtwRegHandle )
  {
    v16[0] = 0;
    dwProcessId = 0;
    if ( GetWindowThreadProcessId(a2, &dwProcessId) )
    {
      SystemInformation = (_WORD *)dwProcessId;
      v13 = 17039360;
      v14 = (int *)v16;
      if ( NtQuerySystemInformation(SystemProcessIdInformation, &SystemInformation, 0x18u, 0) >= 0 )
      {
        v4 = v16[0];
        v5 = v16;
        if ( !v16[0] )
          goto LABEL_10;
        v6 = v16;
        do
        {
          ++v6;
          if ( v4 == 92 )
            v5 = v6;
          v4 = *v6;
        }
        while ( *v6 );
        if ( v5 )
        {
LABEL_10:
          v7 = 260;
          v8 = v5;
          v9 = 1;
          do
          {
            if ( !*v8 )
              break;
            ++v8;
            --v7;
          }
          while ( v7 );
          if ( v7 )
          {
            SystemInformation = v5;
            v13 = 2 * ((260 - (_DWORD)v7) & (unsigned int)-(v7 != 0)) + 2;
            if ( a1 == 2 )
            {
              v10 = AppHungEvent;
            }
            else
            {
              v15 = 4;
              v14 = &v17;
              v10 = AppVetoEvent;
              v9 = 2;
            }
            EtwEventWrite(g_EtwRegHandle, v10, v9, &SystemInformation);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180006208  mov     [rsp-8+arg_0], rbx
0x18000620d  mov     [rsp-8+arg_10], r8d
0x180006212  push    rbp
0x180006213  push    rsi
0x180006214  push    rdi
0x180006215  lea     rbp, [rsp-170h]
0x18000621d  sub     rsp, 270h
0x180006224  mov     rax, cs:__security_cookie
0x18000622b  xor     rax, rsp
0x18000622e  mov     [rbp+180h+var_20], rax
0x180006235  xor     esi, esi
0x180006237  mov     r8, rdx
0x18000623a  cmp     cs:g_EtwRegHandle, rsi
0x180006241  mov     edi, ecx
0x180006243  jz      loc_180006377
0x180006249  lea     rdx, [rsp+280h+dwProcessId]; lpdwProcessId
0x18000624e  mov     [rsp+280h+var_230], si
0x180006253  mov     rcx, r8; hWnd
0x180006256  mov     [rsp+280h+dwProcessId], esi
0x18000625a  call    cs:__imp_GetWindowThreadProcessId
0x180006261  nop     dword ptr [rax+rax+00h]
0x180006266  test    eax, eax
0x180006268  jz      loc_180006377
0x18000626e  mov     eax, [rsp+280h+dwProcessId]
0x180006272  lea     r8d, [rsi+18h]; SystemInformationLength
0x180006276  mov     [rsp+280h+SystemInformation], rax
0x18000627b  lea     rdx, [rsp+280h+SystemInformation]; SystemInformation
0x180006280  lea     rax, [rsp+280h+var_230]
0x180006285  mov     [rsp+280h+var_250], 1040000h
0x18000628e  xor     r9d, r9d; ReturnLength
0x180006291  mov     [rsp+280h+var_248], rax
0x180006296  lea     ecx, [rsi+58h]; SystemInformationClass
0x180006299  mov     ebx, 104h
0x18000629e  call    cs:__imp_NtQuerySystemInformation
0x1800062a5  nop     dword ptr [rax+rax+00h]
0x1800062aa  test    eax, eax
0x1800062ac  js      loc_180006377
0x1800062b2  movzx   r8d, [rsp+280h+var_230]
0x1800062b8  lea     rcx, [rsp+280h+var_230]
0x1800062bd  cmp     si, r8w
0x1800062c1  jz      short loc_1800062ED
0x1800062c3  lea     rdx, [rsp+280h+var_230]
0x1800062c8  add     rdx, 2
0x1800062cc  mov     eax, 5Ch ; '\'
0x1800062d1  cmp     ax, r8w
0x1800062d5  jnz     short loc_1800062DA
0x1800062d7  mov     rcx, rdx
0x1800062da  movzx   r8d, word ptr [rdx]
0x1800062de  cmp     si, r8w
0x1800062e2  jnz     short loc_1800062C8
0x1800062e4  test    rcx, rcx
0x1800062e7  jz      loc_180006377
0x1800062ed  mov     rdx, rbx
0x1800062f0  mov     rax, rcx
0x1800062f3  mov     r8d, 1
0x1800062f9  cmp     [rax], si
0x1800062fc  jz      short loc_180006307
0x1800062fe  add     rax, 2
0x180006302  sub     rdx, r8
0x180006305  jnz     short loc_1800062F9
0x180006307  sub     rbx, rdx
0x18000630a  mov     rax, rdx
0x18000630d  neg     rax
0x180006310  sbb     rax, rax
0x180006313  and     rax, rbx
0x180006316  test    rdx, rdx
0x180006319  jz      short loc_180006377
0x18000631b  mov     [rsp+280h+SystemInformation], rcx
0x180006320  lea     eax, ds:2[rax*2]
0x180006327  mov     dword ptr [rsp+280h+var_250], eax
0x18000632b  mov     dword ptr [rsp+280h+var_250+4], esi
0x18000632f  cmp     edi, 2
0x180006332  jnz     short loc_18000633D
0x180006334  lea     rdx, AppHungEvent
0x18000633b  jmp     short loc_18000635F
0x18000633d  lea     rax, [rbp+180h+arg_10]
0x180006344  mov     [rsp+280h+var_240], 4
0x18000634d  mov     [rsp+280h+var_248], rax
0x180006352  lea     rdx, AppVetoEvent
0x180006359  mov     r8d, 2
0x18000635f  mov     rcx, cs:g_EtwRegHandle
0x180006366  lea     r9, [rsp+280h+SystemInformation]
0x18000636b  call    cs:__imp_EtwEventWrite
0x180006372  nop     dword ptr [rax+rax+00h]
0x180006377  mov     rcx, [rbp+180h+var_20]
0x18000637e  xor     rcx, rsp; StackCookie
0x180006381  call    __security_check_cookie
0x180006386  mov     rbx, [rsp+280h+arg_0]
0x18000638e  add     rsp, 270h
0x180006395  pop     rdi
0x180006396  pop     rsi
0x180006397  pop     rbp
0x180006398  retn
```
