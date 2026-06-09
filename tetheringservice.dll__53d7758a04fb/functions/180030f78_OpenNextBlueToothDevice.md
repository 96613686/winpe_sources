# OpenNextBlueToothDevice

- ea: `0x180030f78`
- end: `0x18003118a`
- name: `OpenNextBlueToothDevice`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180030c14`

## callees

- `0x180002590`
- `0x180003088`
- `0x18003017c`
- `0x180030e58`
- `0x180030f14`
- `0x180030f78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031034`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030ffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003102a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030ffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003102a`

## pseudocode

```c
DWORD __fastcall OpenNextBlueToothDevice(_QWORD *a1, _OWORD *a2)
{
  DWORD result; // eax
  HANDLE v5; // rdi
  int DeviceConfig; // ebx
  char *v7; // rax
  char *v8; // rbx
  char *v9; // rcx
  __int64 v10; // rdx
  __int128 v11; // xmm1
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  HANDLE hObject[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v16; // [rsp+36h] [rbp-CAh]
  __int128 v17; // [rsp+46h] [rbp-BAh]
  __int128 v18; // [rsp+56h] [rbp-AAh]
  __int128 v19; // [rsp+66h] [rbp-9Ah]
  __int128 v20; // [rsp+76h] [rbp-8Ah]
  __int128 v21; // [rsp+86h] [rbp-7Ah]
  int v22; // [rsp+96h] [rbp-6Ah]
  char v23; // [rsp+9Ah] [rbp-66h] BYREF

  memset_0(&v15, 0, 0x1FAu);
  hObject[0] = (HANDLE)-1LL;
  *a1 = 0;
  result = OpenBthpanHandle(hObject);
  if ( !result )
  {
    v5 = hObject[0];
    DeviceConfig = GetDeviceConfig(hObject[0], a2, &v15);
    if ( DeviceConfig )
    {
      if ( !CloseHandle(v5) )
        GetLastError();
      return DeviceConfig;
    }
    else
    {
      v7 = (char *)BTAllocMem(0x288u);
      v8 = v7;
      if ( v7 )
      {
        memset_0(v7, 0, 0x288u);
        v9 = &v23;
        v10 = 3;
        *(_OWORD *)(v8 + 52) = *a2;
        *(_OWORD *)(v8 + 68) = a2[1];
        *(_OWORD *)(v8 + 84) = a2[2];
        *(_OWORD *)(v8 + 100) = a2[3];
        *(_OWORD *)(v8 + 116) = a2[4];
        v11 = *(_OWORD *)((char *)a2 + 78);
        *((_QWORD *)v8 + 2) = v5;
        *(_OWORD *)(v8 + 130) = v11;
        *((_WORD *)v8 + 72) = 0;
        *((_DWORD *)v8 + 12) = v15;
        *(_OWORD *)(v8 + 146) = v16;
        *(_OWORD *)(v8 + 162) = v17;
        *(_OWORD *)(v8 + 178) = v18;
        *(_OWORD *)(v8 + 194) = v19;
        *(_OWORD *)(v8 + 210) = v20;
        *(_OWORD *)(v8 + 226) = v21;
        *(_DWORD *)(v8 + 242) = v22;
        *((_WORD *)v8 + 122) = 0;
        v12 = v8 + 246;
        do
        {
          *v12 = *(_OWORD *)v9;
          v12[1] = *((_OWORD *)v9 + 1);
          v12[2] = *((_OWORD *)v9 + 2);
          v12[3] = *((_OWORD *)v9 + 3);
          v12[4] = *((_OWORD *)v9 + 4);
          v12[5] = *((_OWORD *)v9 + 5);
          v12[6] = *((_OWORD *)v9 + 6);
          v13 = *((_OWORD *)v9 + 7);
          v9 += 128;
          v12[7] = v13;
          v12 += 8;
          --v10;
        }
        while ( v10 );
        *v12 = *(_OWORD *)v9;
        result = 0;
        *((_WORD *)v8 + 322) = 0;
        *a1 = v8;
      }
      else
      {
        if ( !CloseHandle(v5) )
          GetLastError();
        return 14;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030f78  mov     [rsp-8+arg_10], rbx
0x180030f7d  mov     [rsp-8+arg_18], rsi
0x180030f82  push    rbp
0x180030f83  push    rdi
0x180030f84  push    r14
0x180030f86  lea     rbp, [rsp-140h]
0x180030f8e  sub     rsp, 240h
0x180030f95  mov     rax, cs:__security_cookie
0x180030f9c  xor     rax, rsp
0x180030f9f  mov     [rbp+150h+var_20], rax
0x180030fa6  mov     rsi, rdx
0x180030fa9  mov     r14, rcx
0x180030fac  xor     edx, edx; Val
0x180030fae  lea     rcx, [rsp+250h+var_220]; void *
0x180030fb3  mov     r8d, 1FAh; Size
0x180030fb9  call    memset_0
0x180030fbe  lea     rcx, [rsp+250h+hObject]
0x180030fc3  mov     [rsp+250h+hObject], 0FFFFFFFFFFFFFFFFh
0x180030fcc  mov     qword ptr [r14], 0
0x180030fd3  call    OpenBthpanHandle
0x180030fd8  test    eax, eax
0x180030fda  jnz     loc_180031163
0x180030fe0  mov     rdi, [rsp+250h+hObject]
0x180030fe5  lea     r8, [rsp+250h+var_220]
0x180030fea  mov     rcx, rdi
0x180030fed  mov     rdx, rsi
0x180030ff0  call    GetDeviceConfig
0x180030ff5  mov     ebx, eax
0x180030ff7  test    eax, eax
0x180030ff9  jz      short loc_180031015
0x180030ffb  mov     rcx, rdi; hObject
0x180030ffe  call    cs:__imp_CloseHandle
0x180031004  test    eax, eax
0x180031006  jnz     short loc_18003100E
0x180031008  call    cs:__imp_GetLastError
0x18003100e  mov     eax, ebx
0x180031010  jmp     loc_180031163
0x180031015  mov     ecx, 288h; Size
0x18003101a  call    BTAllocMem
0x18003101f  mov     rbx, rax
0x180031022  test    rax, rax
0x180031025  jnz     short loc_180031044
0x180031027  mov     rcx, rdi; hObject
0x18003102a  call    cs:__imp_CloseHandle
0x180031030  test    eax, eax
0x180031032  jnz     short loc_18003103A
0x180031034  call    cs:__imp_GetLastError
0x18003103a  mov     eax, 0Eh
0x18003103f  jmp     loc_180031163
0x180031044  xor     edx, edx; Val
0x180031046  mov     r8d, 288h; Size
0x18003104c  mov     rcx, rbx; void *
0x18003104f  call    memset_0
0x180031054  movups  xmm0, xmmword ptr [rsi]
0x180031057  xor     eax, eax
0x180031059  lea     rcx, [rbp+150h+var_1B6]
0x18003105d  mov     edx, 3
0x180031062  movups  xmmword ptr [rbx+34h], xmm0
0x180031066  movups  xmm1, xmmword ptr [rsi+10h]
0x18003106a  lea     r8d, [rdx+7Dh]
0x18003106e  movups  xmmword ptr [rbx+44h], xmm1
0x180031072  movups  xmm0, xmmword ptr [rsi+20h]
0x180031076  movups  xmmword ptr [rbx+54h], xmm0
0x18003107a  movups  xmm1, xmmword ptr [rsi+30h]
0x18003107e  movups  xmmword ptr [rbx+64h], xmm1
0x180031082  movups  xmm0, xmmword ptr [rsi+40h]
0x180031086  movups  xmmword ptr [rbx+74h], xmm0
0x18003108a  movups  xmm1, xmmword ptr [rsi+4Eh]
0x18003108e  mov     [rbx+10h], rdi
0x180031092  movups  xmmword ptr [rbx+82h], xmm1
0x180031099  mov     [rbx+90h], ax
0x1800310a0  mov     eax, [rsp+250h+var_220]
0x1800310a4  mov     [rbx+30h], eax
0x1800310a7  movups  xmm0, [rsp+250h+var_21A]
0x1800310ac  movups  xmmword ptr [rbx+92h], xmm0
0x1800310b3  movups  xmm1, [rsp+250h+var_20A]
0x1800310b8  movups  xmmword ptr [rbx+0A2h], xmm1
0x1800310bf  movups  xmm0, [rsp+250h+var_1FA]
0x1800310c4  movups  xmmword ptr [rbx+0B2h], xmm0
0x1800310cb  movups  xmm1, [rsp+250h+var_1EA]
0x1800310d0  movups  xmmword ptr [rbx+0C2h], xmm1
0x1800310d7  movups  xmm0, [rsp+250h+var_1DA]
0x1800310dc  movups  xmmword ptr [rbx+0D2h], xmm0
0x1800310e3  movups  xmm1, [rbp+150h+var_1CA]
0x1800310e7  movups  xmmword ptr [rbx+0E2h], xmm1
0x1800310ee  mov     eax, [rbp+150h+var_1BA]
0x1800310f1  mov     [rbx+0F2h], eax
0x1800310f7  xor     eax, eax
0x1800310f9  mov     [rbx+0F4h], ax
0x180031100  lea     rax, [rbx+0F6h]
0x180031107  movups  xmm0, xmmword ptr [rcx]
0x18003110a  movups  xmmword ptr [rax], xmm0
0x18003110d  movups  xmm1, xmmword ptr [rcx+10h]
0x180031111  movups  xmmword ptr [rax+10h], xmm1
0x180031115  movups  xmm0, xmmword ptr [rcx+20h]
0x180031119  movups  xmmword ptr [rax+20h], xmm0
0x18003111d  movups  xmm1, xmmword ptr [rcx+30h]
0x180031121  movups  xmmword ptr [rax+30h], xmm1
0x180031125  movups  xmm0, xmmword ptr [rcx+40h]
0x180031129  movups  xmmword ptr [rax+40h], xmm0
0x18003112d  movups  xmm1, xmmword ptr [rcx+50h]
0x180031131  movups  xmmword ptr [rax+50h], xmm1
0x180031135  movups  xmm0, xmmword ptr [rcx+60h]
0x180031139  movups  xmmword ptr [rax+60h], xmm0
0x18003113d  movups  xmm1, xmmword ptr [rcx+70h]
0x180031141  add     rcx, r8
0x180031144  movups  xmmword ptr [rax+70h], xmm1
0x180031148  add     rax, r8
0x18003114b  sub     rdx, 1
0x18003114f  jnz     short loc_180031107
0x180031151  movups  xmm0, xmmword ptr [rcx]
0x180031154  movups  xmmword ptr [rax], xmm0
0x180031157  xor     eax, eax
0x180031159  mov     [rbx+284h], ax
0x180031160  mov     [r14], rbx
0x180031163  mov     rcx, [rbp+150h+var_20]
0x18003116a  xor     rcx, rsp; StackCookie
0x18003116d  call    __security_check_cookie
0x180031172  lea     r11, [rsp+250h+var_10]
0x18003117a  mov     rbx, [r11+30h]
0x18003117e  mov     rsi, [r11+38h]
0x180031182  mov     rsp, r11
0x180031185  pop     r14
0x180031187  pop     rdi
0x180031188  pop     rbp
0x180031189  retn
```
