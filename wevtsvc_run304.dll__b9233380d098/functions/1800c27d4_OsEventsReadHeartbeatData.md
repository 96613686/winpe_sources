# OsEventsReadHeartbeatData

- ea: `0x1800c27d4`
- end: `0x1800c29cf`
- name: `OsEventsReadHeartbeatData`
- size: `507`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180093d78`
- `0x1800940d0`

## callees

- `0x180004a3c`
- `0x180017b60`
- `0x18003420c`
- `0x18005fc9c`
- `0x180092008`
- `0x18009aee0`
- `0x1800c27d4`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x1800c290f`
- `ntdll!RtlComputeCrc32` at `0x1800c290f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c28d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c28d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2961`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c28a8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c28a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c2860`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c2860`

## pseudocode

```c
char __fastcall OsEventsReadHeartbeatData(__int64 a1)
{
  char v3; // si
  int i; // edi
  HANDLE FileW; // rax
  DWORD v6; // eax
  ULONG v7; // eax
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  char LastError; // al
  HANDLE v11; // [rsp+40h] [rbp-29h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-21h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+50h] [rbp-19h] BYREF
  _OWORD Buffer[3]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v15; // [rsp+A0h] [rbp+37h]

  if ( g_bHeartBeatsDisabled )
    return 0;
  v3 = 0;
  *(_DWORD *)(a1 + 16) = 0;
  for ( i = 0; i <= 2; ++i )
  {
    GetNameForHeartBeatFile(lpFileName, (unsigned int)i);
    if ( lpFileName[0] != lpFileName[1] )
    {
      FileW = CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, 0x80u, 0);
      v11 = FileW;
      if ( (unsigned __int64)FileW + 1 <= 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids,
            lpFileName[0],
            LastError);
        }
      }
      else
      {
        NumberOfBytesRead = 0;
        v15 = 0;
        memset(Buffer, 0, sizeof(Buffer));
        if ( ReadFile(FileW, Buffer, 0x38u, &NumberOfBytesRead, 0) )
        {
          v7 = RtlComputeCrc32(0, (PUCHAR)Buffer, 0x30u);
          if ( (_DWORD)v15 == v7 && LODWORD(Buffer[1]) > *(_DWORD *)(a1 + 16) )
          {
            v8 = Buffer[0];
            *(_DWORD *)(a1 + 16) = Buffer[1];
            v3 = 1;
            v9 = Buffer[2];
            *(_OWORD *)a1 = v8;
            *(_OWORD *)(a1 + 20) = *(_OWORD *)((char *)&Buffer[1] + 4);
            *(_OWORD *)(a1 + 32) = v9;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, v6);
        }
      }
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v11);
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  }
  return v3;
}

```

## disassembly

```asm
0x1800c27d4  mov     [rsp-8+arg_8], rbx
0x1800c27d9  mov     [rsp-8+arg_10], rsi
0x1800c27de  push    rbp
0x1800c27df  push    rdi
0x1800c27e0  push    r12
0x1800c27e2  lea     rbp, [rsp-47h]
0x1800c27e7  sub     rsp, 0B0h
0x1800c27ee  mov     rax, cs:__security_cookie
0x1800c27f5  xor     rax, rsp
0x1800c27f8  mov     [rbp+57h+var_18], rax
0x1800c27fc  cmp     cs:?g_bHeartBeatsDisabled@@3_NA, 0; bool g_bHeartBeatsDisabled
0x1800c2803  mov     rbx, rcx
0x1800c2806  jz      short loc_1800C280F
0x1800c2808  xor     al, al
0x1800c280a  jmp     loc_1800C29AB
0x1800c280f  xor     sil, sil
0x1800c2812  mov     dword ptr [rcx+10h], 0
0x1800c2819  xor     edi, edi
0x1800c281b  lea     r12, WPP_GLOBAL_Control
0x1800c2822  mov     edx, edi
0x1800c2824  lea     rcx, [rbp+57h+lpFileName]
0x1800c2828  call    GetNameForHeartBeatFile
0x1800c282d  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800c2831  cmp     rcx, [rbp+57h+var_68]
0x1800c2835  jz      loc_1800C2994
0x1800c283b  xor     r9d, r9d; lpSecurityAttributes
0x1800c283e  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1800c2847  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c284f  mov     edx, 80000000h; dwDesiredAccess
0x1800c2854  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c285c  lea     r8d, [r9+1]; dwShareMode
0x1800c2860  call    cs:__imp_CreateFileW
0x1800c2866  mov     [rbp+57h+var_80], rax
0x1800c286a  lea     rcx, [rax+1]
0x1800c286e  cmp     rcx, 1
0x1800c2872  jbe     loc_1800C2946
0x1800c2878  xor     ecx, ecx
0x1800c287a  mov     [rbp+57h+NumberOfBytesRead], 0
0x1800c2881  xorps   xmm0, xmm0
0x1800c2884  mov     [rbp+57h+var_20], rcx
0x1800c2888  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx; lpOverlapped
0x1800c288d  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800c2891  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x1800c2895  lea     r8d, [rcx+38h]; nNumberOfBytesToRead
0x1800c2899  mov     rcx, rax; hFile
0x1800c289c  movups  [rbp+57h+Buffer], xmm0
0x1800c28a0  movups  [rbp+57h+var_40], xmm0
0x1800c28a4  movups  [rbp+57h+var_30], xmm0
0x1800c28a8  call    cs:__imp_ReadFile
0x1800c28ae  test    eax, eax
0x1800c28b0  jnz     short loc_1800C2903
0x1800c28b2  mov     rax, cs:WPP_GLOBAL_Control
0x1800c28b9  cmp     rax, r12
0x1800c28bc  jz      loc_1800C298B
0x1800c28c2  test    dword ptr [rax+1Ch], 4000h
0x1800c28c9  jz      loc_1800C298B
0x1800c28cf  cmp     byte ptr [rax+19h], 2
0x1800c28d3  jb      loc_1800C298B
0x1800c28d9  call    cs:__imp_GetLastError
0x1800c28df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c28e6  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x1800c28ed  mov     edx, 17h
0x1800c28f2  mov     r9d, eax
0x1800c28f5  mov     rcx, [rcx+10h]
0x1800c28f9  call    WPP_SF_d
0x1800c28fe  jmp     loc_1800C298B
0x1800c2903  mov     r8d, 30h ; '0'; Length
0x1800c2909  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800c290d  xor     ecx, ecx; InitialCrc
0x1800c290f  call    cs:__imp_RtlComputeCrc32
0x1800c2915  cmp     dword ptr [rbp+57h+var_20], eax
0x1800c2918  jnz     short loc_1800C298B
0x1800c291a  mov     eax, dword ptr [rbp+57h+var_40]
0x1800c291d  lea     rcx, [rbp+57h+var_80]
0x1800c2921  cmp     eax, [rbx+10h]
0x1800c2924  jbe     short loc_1800C298F
0x1800c2926  movups  xmm0, [rbp+57h+Buffer]
0x1800c292a  mov     [rbx+10h], eax
0x1800c292d  mov     sil, 1
0x1800c2930  movups  xmm1, [rbp+57h+var_30]
0x1800c2934  movdqu  xmmword ptr [rbx], xmm0
0x1800c2938  movups  xmm0, [rbp+57h+var_40+4]
0x1800c293c  movups  xmmword ptr [rbx+14h], xmm0
0x1800c2940  movups  xmmword ptr [rbx+20h], xmm1
0x1800c2944  jmp     short loc_1800C298F
0x1800c2946  mov     rax, cs:WPP_GLOBAL_Control
0x1800c294d  cmp     rax, r12
0x1800c2950  jz      short loc_1800C298B
0x1800c2952  test    dword ptr [rax+1Ch], 4000h
0x1800c2959  jz      short loc_1800C298B
0x1800c295b  cmp     byte ptr [rax+19h], 2
0x1800c295f  jb      short loc_1800C298B
0x1800c2961  call    cs:__imp_GetLastError
0x1800c2967  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c296e  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x1800c2975  mov     r9, [rbp+57h+lpFileName]
0x1800c2979  mov     edx, 16h
0x1800c297e  mov     [rsp+0C0h+dwCreationDisposition], eax
0x1800c2982  mov     rcx, [rcx+10h]
0x1800c2986  call    WPP_SF_Sd
0x1800c298b  lea     rcx, [rbp+57h+var_80]
0x1800c298f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800c2994  lea     rcx, [rbp+57h+lpFileName]; void *
0x1800c2998  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800c299d  inc     edi
0x1800c299f  cmp     edi, 2
0x1800c29a2  jle     loc_1800C2822
0x1800c29a8  mov     al, sil
0x1800c29ab  mov     rcx, [rbp+57h+var_18]
0x1800c29af  xor     rcx, rsp; StackCookie
0x1800c29b2  call    __security_check_cookie
0x1800c29b7  lea     r11, [rsp+0C0h+var_10]
0x1800c29bf  mov     rbx, [r11+28h]
0x1800c29c3  mov     rsi, [r11+30h]
0x1800c29c7  mov     rsp, r11
0x1800c29ca  pop     r12
0x1800c29cc  pop     rdi
0x1800c29cd  pop     rbp
0x1800c29ce  retn
```
