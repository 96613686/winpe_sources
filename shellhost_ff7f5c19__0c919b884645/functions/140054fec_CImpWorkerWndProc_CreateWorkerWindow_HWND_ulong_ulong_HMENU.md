# CImpWorkerWndProc::CreateWorkerWindow(HWND__ *,ulong,ulong,HMENU__ *)

- ea: `0x140054fec`
- end: `0x140055080`
- name: `?CreateWorkerWindow@CImpWorkerWndProc@@IEAAPEAUHWND__@@PEAU2@KKPEAUHMENU__@@@Z`
- size: `148`
- prototype: `HWND __fastcall(CImpWorkerWndProc *__hidden this, HWND, unsigned int, unsigned int, HMENU)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400578bc`

## callees

- `0x140054b84`
- `0x140054fec`

## import_xrefs

- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x14005502a`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x140055070`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x14005502a`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x140055070`

## pseudocode

```c
HWND __fastcall CImpWorkerWndProc::CreateWorkerWindow(CImpWorkerWndProc *this, HWND a2)
{
  HWND result; // rax

  result = (HWND)*((_QWORD *)this + 1);
  if ( !result )
  {
    if ( *((_BYTE *)this + 16) )
    {
      if ( *((_QWORD *)this + 4)
        && *((_QWORD *)this + 3)
        && (result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, -3, 0),
            (*((_QWORD *)this + 1) = result) != 0) )
      {
        if ( *((_BYTE *)this + 16) )
        {
          CImpWorkerWndProc::AddWndRef(this);
          return (HWND)*((_QWORD *)this + 1);
        }
      }
      else
      {
        return 0;
      }
    }
    else
    {
      result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, -3, 0);
      *((_QWORD *)this + 1) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140054fec  push    rbx
0x140054fee  sub     rsp, 30h
0x140054ff2  mov     rax, [rcx+8]
0x140054ff6  mov     rbx, rcx
0x140054ff9  test    rax, rax
0x140054ffc  jnz     short loc_14005507A
0x140054ffe  cmp     [rcx+10h], al
0x140055001  jz      short loc_140055051
0x140055003  cmp     [rcx+20h], rax
0x140055007  jz      short loc_14005504D
0x140055009  cmp     [rcx+18h], rax
0x14005500d  jz      short loc_14005504D
0x14005500f  mov     [rsp+38h+var_10], rcx
0x140055014  lea     rdx, [rax-3]
0x140055018  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14005501f  mov     [rsp+38h+var_18], rax
0x140055024  xor     r9d, r9d
0x140055027  xor     r8d, r8d
0x14005502a  call    cs:__imp_SHCreateWorkerWindowW
0x140055030  mov     [rbx+8], rax
0x140055034  test    rax, rax
0x140055037  jz      short loc_14005504D
0x140055039  cmp     byte ptr [rbx+10h], 0
0x14005503d  jz      short loc_14005507A
0x14005503f  mov     rcx, rbx; this
0x140055042  call    ?AddWndRef@CImpWorkerWndProc@@AEAAXXZ; CImpWorkerWndProc::AddWndRef(void)
0x140055047  mov     rax, [rbx+8]
0x14005504b  jmp     short loc_14005507A
0x14005504d  xor     eax, eax
0x14005504f  jmp     short loc_14005507A
0x140055051  xor     r9d, r9d
0x140055054  mov     [rsp+38h+var_10], rbx
0x140055059  xor     r8d, r8d
0x14005505c  mov     [rsp+38h+var_18], 0
0x140055065  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14005506c  lea     rdx, [r9-3]
0x140055070  call    cs:__imp_SHCreateWorkerWindowW
0x140055076  mov     [rbx+8], rax
0x14005507a  add     rsp, 30h
0x14005507e  pop     rbx
0x14005507f  retn
```
